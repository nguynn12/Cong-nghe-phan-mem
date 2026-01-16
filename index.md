# Chương 1. Giới thiệu về công nghệ phần mềm

## 1.7 Bài tập và câu hỏi

<b>Bài 1. Bạn sẽ lựa chọn theo Công nghệ phần mềm hay Khoa học máy tính? Tại sao?</b>

Tôi lựa chọn theo **Công nghệ phần mềm**. Vì tôi thích việc tạo ra các sản phẩm ứng dụng thực tế để giải quyết vấn đề cho người dùng. Tôi quan tâm đến quy trình làm ra phần mềm, từ lúc lấy yêu cầu, thiết kế hệ thống cho đến khi kiểm thử và bảo trì, cũng như cách làm việc nhóm hiệu quả trong dự án.

<b>Câu 1.1 Dưới đây là các giai đoạn phát triển phần mềm. Phát biểu nào không đúng?</b>
A. Lấy và phân tích yêu cầu; Thiết kế
B. Lập trình; Kiểm thử
<mark>C. Họp nhóm dự án</mark>
D. Triển khai; Vận hành và Bảo trì

> *Giải thích: "Họp nhóm" là một hoạt động diễn ra thường xuyên trong quá trình làm việc, không phải là tên một giai đoạn chính thức (Phase) trong vòng đời phát triển phần mềm (SDLC - Software Development life Cycle).*

<b>Câu 1.2 Một số thách thức của các dự án CNPM. Phát biểu nào không đúng?</b>
A. Vượt quá ngân sách
B. Trễ tiến độ
C. Chất lượng kém
<mark>D. Dễ bảo trì</mark>

> *Giải thích: "Dễ bảo trì" là mục tiêu tốt mà phần mềm hướng tới. Thách thức (khó khăn) của dự án phải là "Khó bảo trì" hoặc "Chi phí bảo trì cao".*

<b>Câu 1.3 Một phần mềm như thế nào là có chất lượng? Phát biểu nào không đúng?</b>
A. Tính hiệu quả (efficiency)
<mark>B. Tính khó bảo trì (non maintainability)</mark>
C. Tính bảo mật và tin cậy (security & reliability)
D. Tính dễ sử dụng (usability)

> *Giải thích: Phần mềm chất lượng phải CÓ tính bảo trì (Maintainability). Tính "khó bảo trì" là đặc điểm của phần mềm kém chất lượng.*

# Chương 2. Các mô hình phát triển phần mềm

### Bài tập 2a. Vẽ lại sơ đồ các mô hình

**1. Mô hình Thác nước (Waterfall Model)**

<pre class="mermaid">
graph TD
    A[Requirements] --> B[System Design]
    B --> C[Implementation]
    C --> D[Integration & Testing]
    D --> E[Deployment of System]
    E --> F[Maintenance]
</pre>

**2. Mô hình Chữ V (V-Model)**

<pre class="mermaid">
graph TD
    subgraph Development Phase
    A[Requirements Analysis] --> B[System Design]
    B --> C[Architecture Design]
    C --> D[Module Design]
    end
    
    D --> E[Coding]
    
    subgraph Testing Phase
    E --> F[Unit Testing]
    F --> G[Integration Testing]
    G --> H[System Testing]
    H --> I[Acceptance Testing]
    end

    %% Các đường liên kết ngang thể hiện sự tương ứng (Validation)
    A -.-> I
    B -.-> H
    C -.-> G
    D -.-> F
</pre>

**3. Mô hình Tăng trưởng lặp (Iterative Model)**

<pre class="mermaid">
graph LR
    A((Start)) --> B[Initial Planning]
    B --> C{Iteration Cycle}
    C --> D[Planning]
    D --> E[Requirements]
    E --> F[Analysis & Design]
    F --> G[Implementation]
    G --> H[Testing]
    H --> I[Evaluation]
    I --> C
    I --> J((End/Deploy))
</pre>

**4. Mô hình Agile / Scrum**

<pre class="mermaid">
graph LR
    A[Product Backlog] --> B[Sprint Planning]
    B --> C[Sprint Backlog]
    subgraph Sprint [Sprint (1-4 Weeks)]
        D[Design] --> E[Develop]
        E --> F[Test]
        F --> D
    end
    C --> D
    F --> G[Daily Scrum]
    G --> H[Shippable Product]
    H --> I[Sprint Review]
    I --> J[Sprint Retrospective]
</pre>

---

### Bài tập 2b. Mô tả công việc và công cụ mô hình Thác nước

| Giai đoạn | Mô tả công việc | Công cụ thường dùng |
| :--- | :--- | :--- |
| **Requirements** | Thu thập và phân tích yêu cầu từ khách hàng, xác định hệ thống cần làm gì. | Microsoft Word, Google Docs, Jira, Trello |
| **System Design** | Thiết kế kiến trúc hệ thống, cơ sở dữ liệu, giao diện dựa trên yêu cầu. | Microsoft Visio, Draw.io, Figma, Adobe XD |
| **Implementation** | Lập trình viên viết mã nguồn (coding) để tạo ra phần mềm. | VS Code, IntelliJ, Visual Studio, Git |
| **Testing** | Kiểm thử phần mềm để tìm lỗi (bugs) và đảm bảo đáp ứng yêu cầu. | Selenium, JUnit, TestRail |
| **Deployment** | Cài đặt phần mềm lên môi trường thực tế cho khách hàng sử dụng. | Docker, Jenkins, AWS, Azure |
| **Maintenance** | Bảo trì, sửa lỗi phát sinh và nâng cấp phần mềm sau khi bàn giao. | Jira Service Desk, Zendesk |

---

### Câu hỏi trắc nghiệm

<b>Câu 2.1 Về mô hình Thác nước. Phát biểu nào không đúng?</b>
A. Mỗi giai đoạn phải được hoàn thành trước khi chuyển sang giai đoạn tiếp theo và không có sự quay lại
<mark>B. Không phù hợp với các dự án có yêu cầu ổn định, đã được xác định rõ ràng ngay từ đầu và không có khả năng thay đổi</mark>
C. Đây là mô hình tuần tự, các giai đoạn phát triển diễn ra theo một trình tự tuyến tính, từ trên xuống dưới như một dòng thác
D. Phù hợp với các dự án có yêu cầu ổn định, đã được xác định rõ ràng ngay từ đầu và không có khả năng thay đổi

> *Giải thích: Đáp án B sai vì mô hình Thác nước RẤT phù hợp với dự án ổn định (trái ngược với ý B).*

<b>Câu 2.2 Trong mô hình chữ V có đề cập tới 4 loại kiểm thử. Loại kiểm thử nào sau đây không đúng?</b>
A. Acceptance Testing
<mark>B. Coding Testing</mark>
C. System Testing
D. Integration Testing

> *Giải thích: Trong V-Model, mức thấp nhất là Unit Testing (Kiểm thử đơn vị), không gọi là Coding Testing.*

<b>Câu 2.3 Mô hình tiếp cận lặp gồm các công đoạn sau. Phát biểu nào không đúng?</b>
A. Requirements
<mark>B. Integration</mark>
C. Design & Development
D. Testing

> *Lưu ý: Câu này tùy thuộc vào giáo trình của bạn. Tuy nhiên, thông thường các bước chính là: Requirement -> Design -> Dev -> Test. Integration thường nằm trong Dev hoặc Test chứ không đứng riêng lẻ ngang hàng với Requirement trong tên gọi các pha lớn.*

<b>Câu 2.4 Trong mô hình Agile/Scrum. Phát biểu nào sau đây không đúng?</b>
<mark>A. Scope: xác định phạm vi của biến</mark>
B. Sprint: một chu kỳ phát triển ngắn, thường là 1 tới 4 tuần
C. Product backlog: danh mục các chức năng của sản phẩm
D. Sprint backlog: danh mục các chức năng của một sprint

> *Giải thích: "Scope" trong quản lý dự án là "Phạm vi dự án" (những việc cần làm), không phải là phạm vi của biến (variable scope) trong lập trình.*

