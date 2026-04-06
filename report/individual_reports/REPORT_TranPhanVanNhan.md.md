# Individual Report: Lab 3 - Chatbot vs ReAct Agent

- **Student Name**: TRẦN PHAN VĂN NHÂN
- **Student ID**: 2A202600301
- **Date**: 03/04/2026

---

## I. Technical Contribution (15 Points)

*Describe your specific contribution to the codebase (e.g., implemented a specific tool, fixed the parser, etc.).*

- **Modules Implementated**: agent.py
- **Code Highlights**: lab3_2A202600301/src/agent/agent.py
- **Documentation**: Định nghĩa thêm system prompt, hoàn thành các TODO có trong file agent.py

---

## II. Debugging Case Study (10 Points)

*Analyze a specific failure event you encountered during the lab using the logging system.*

- **Problem Description**: Câu trả lời của Agent dài và chưa trả lời đúng trọng tâm như mong muốn 
- **Log Source**: 
```
{"timestamp": "2026-04-06T14:06:25.510791", "event": "AGENT_START", "data": {"input": "Tôi cần tìm quán phở gần khu vực Trâu Quỳ, tôi đang ở tại 39 đường Thành Trung, Trâu Quỳ, Gia Lâm, Hà Nội", "model": "gpt-4o"}}
{"timestamp": "2026-04-06T14:06:27.985107", "event": "LLM_RESPONSE", "data": {"step": 0, "response": {"content": "Thought: Đầu tiên, tôi cần tìm các quán phở tại khu vực Trâu Quỳ, Gia Lâm, Hà Nội.\nAction: websearch_food_locations: {\"food_name\": \"phở\", \"region\": \"Trâu Quỳ, Gia Lâm, Hà Nội\"}\nObservation", "usage": {"prompt_tokens": 926, "completion_tokens": 61, "total_tokens": 987}, "latency_ms": 2473, "provider": "openai"}}}
{"timestamp": "2026-04-06T14:06:27.985578", "event": "LLM_METRIC", "data": {"provider": "openai", "model": "gpt-4o", "prompt_tokens": 926, "completion_tokens": 61, "total_tokens": 987, "latency_ms": 2473, "cost_estimate": 0.00987}}
{"timestamp": "2026-04-06T14:06:27.987001", "event": "ACTION_CALL", "data": {"tool": "websearch_food_locations", "input": "{\"food_name\": \"phở\", \"region\": \"Trâu Quỳ, Gia Lâm, Hà Nội\"}"}}
{"timestamp": "2026-04-06T14:06:29.177507", "event": "OBSERVATION", "data": {"result": ["Địa chỉ: 68 Đ. Trâu Quỳ, TDP Nông Lâm, Gia Lâm, Hà Nội, Việt Nam; Chỉ Đường: Nằm trên đường Trâu Quỳ, gần khu vực Nông Lâm, dễ tìm. Quán có", "Địa chỉ: 64 Nguyễn Khiêm Ích -Khu 31ha- Trâu Quỳ - Gia Lâm - Hà Nội phố này là ngõ 237 phố Ngô Xuân Quảng các bạn nhé! ☎️ Hotline: 0343 588 669.", "Quán vẫn có Gà Đông Tảo hay chân Đông Tảo bán. Phở Gà ABéo - Kiều Văn Thái Địa chỉ: khu 31ha Trâu Qùy, Gia Lâm, Hà Nội.", "+ Bộ sưu tập hình ảnh. Để lưu trữ địa điểm của bạn). 233 Tru Quỳ,    Huyện Gia Lm, Hà Nội. * Lưu vào Bộ sưu tập (0);). * Có giao hàng Có giao hàng. * Có máy lạnh & điều hòa Có máy lạnh & điều hòa. * Có phòng riêng Có phòng riêng. * Có chỗ chơi cho trẻ em Có chỗ chơi cho trẻ em. * Có thẻ thành viên Có thẻ thành viên. Đã được lưu bộ sưu tập. * Chọn bộ sưu tập để lưu lại   loading... * Chọn bộ sưu tập để lưu lại   loading... + Tạo bộ sưu tập mới. 24,623,376 Bộ sưu tập. bộ sưu tập được tạo. Nhanh & tiện lợi - với hàng ngàn địa điểm, bình luận, hình ảnh & thành viên chia sẻ. Lưu ảnh vào bộ sưu tập. Cấu hình bộ sưu tập. Cập nhật bộ sưu tập của bạn Tạo bộ sưu tập mới. Cấu hình bộ sưu tập.", "Trang Trieu nước bên 59 ở Ái mộ nguội, hương vị nhạt nhoà thấy hơi nhiều quế hồi, bánh hơi cứng, thịt chín - gàu thái mỏng quá chỉ sợ quạt thổi"]}}
```
- **Diagnosis**: Có thể là do system prompt chưa đúng với đầu ra mong muốn
- **Solution**: System prompt kĩ hơn + describe tool cụ thể hơn
---

## III. Personal Insights: Chatbot vs ReAct (10 Points)

*Reflect on the reasoning capability difference.*

1.  **Reasoning**: Quay trở lại một lần nữa trước khi đưa ra câu trả lời cho User
2.  **Reliability**: Khi User có sẵn các thông tin ngữ cảnh đầu mà không cần phải suy luận để đưa ra câu trả lời
3.  **Observation**: Giúp đưa ra các quyết định tốt hơn trước khi đưa ra câu trả lời

---

## IV. Future Improvements (5 Points)

*How would you scale this for a production-level AI agent system?*

- **Scalability**: Định nghĩa đầy đủ tool và có bộ điều phối rõ ràng 
- **Safety**: Định nghĩa các trường không được xâm phạm 
- **Performance**: Sử dụng các cấu trúc của Graph để truy vấn thông tin liên quan dễ dàng hơn

---
