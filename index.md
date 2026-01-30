# Chương 1. Giới thiệu về công nghệ phần mềm

## 1.7 Bài tập và câu hỏi

<b>Bài 1. Bạn sẽ lựa chọn theo Công nghệ phần mềm hay Khoa học máy tính? Tại sao?</b>

Tôi lựa chọn theo **Công nghệ phần mềm**. Vì tôi thích việc tạo ra các sản phẩm ứng dụng thực tế để giải quyết vấn đề cho người dùng. Tôi quan tâm đến quy trình làm ra phần mềm, từ lúc lấy yêu cầu, thiết kế hệ thống cho đến khi kiểm thử và bảo trì, cũng như cách làm việc nhóm hiệu quả trong dự án.

<b>Câu 1.1 Dưới đây là các giai đoạn phát triển phần mềm. Phát biểu nào không đúng?</b> <br>
A. Lấy và phân tích yêu cầu; Thiết kế <br>
B. Lập trình; Kiểm thử <br>
<mark>C. Họp nhóm dự án</mark> <br>
D. Triển khai; Vận hành và Bảo trì

> *Giải thích: "Họp nhóm" là một hoạt động giao tiếp diễn ra thường xuyên trong suốt quá trình làm việc, nó không phải là tên một giai đoạn kỹ thuật chính thức (Phase) trong vòng đời phát triển phần mềm (SDLC).*

<b>Câu 1.2 Một số thách thức của các dự án CNPM. Phát biểu nào không đúng?</b> <br>
A. Vượt quá ngân sách <br>
B. Trễ tiến độ <br>
C. Chất lượng kém <br>
<mark>D. Dễ bảo trì</mark>

> *Giải thích: "Dễ bảo trì" là mục tiêu tốt đẹp mà phần mềm hướng tới. Thách thức (khó khăn) của dự án phải là "Khó bảo trì" hoặc "Chi phí bảo trì tốn kém".*

<b>Câu 1.3 Một phần mềm như thế nào là có chất lượng? Phát biểu nào không đúng?</b> <br>
A. Tính hiệu quả (efficiency) <br>
<mark>B. Tính khó bảo trì (non maintainability)</mark> <br>
C. Tính bảo mật và tin cậy (security & reliability) <br>
D. Tính dễ sử dụng (usability)

> *Giải thích: Phần mềm chất lượng phải CÓ tính bảo trì (Maintainability). Tính "khó bảo trì" là đặc điểm của phần mềm kém chất lượng (Legacy code, Spaghetti code).*

# Chương 2. Các mô hình phát triển phần mềm

## 2.5 Bài tập và câu hỏi

### Bài 2a. Vẽ lại sơ đồ các mô hình

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
    %% --- GIAI ĐOẠN CHUẨN BỊ ---
    Start1[Scope] --> Start2[Product Backlog]
    Start2 --> Start3[Design]

    %% --- VÒNG LẶP SCRUM ---
    subgraph ScrumCycle ["SCRUM METHODOLOGY"]
        direction TB
        P1(Sprint Planning meeting) --> P2[Sprint Backlog]
        P2 --> P3[Sprint Execution]
        
        %% Daily Scrum loop
        P3 -- Daily Loop --> P4((Daily Scrum))
        P4 --> P3
        
        P3 --> P5[Sprint Automation]
        P5 --> P6[Sprint Review Meeting]
        P6 --> P7[Sprint Retrospective]
        
        P7 -.-> P1
    end

    %% --- KẾT NỐI RA ---
    Start3 --> P1
    P6 --> EndNode[Usable Software]
</pre>

### Bài 2b. Mô tả công việc và công cụ mô hình Thác nước

| Giai đoạn | Mô tả công việc | Công cụ thường dùng |
| :--- | :--- | :--- |
| **Requirements** | Thu thập và phân tích yêu cầu từ khách hàng. | Word, Google Docs, Jira |
| **System Design** | Thiết kế kiến trúc, CSDL, giao diện. | Visio, Draw.io, Figma |
| **Implementation** | Viết mã nguồn (coding). | VS Code, IntelliJ, Git |
| **Testing** | Kiểm thử tìm lỗi (bugs). | Selenium, JUnit, TestRail |
| **Deployment** | Cài đặt lên môi trường thực tế. | Docker, Jenkins, AWS |
| **Maintenance** | Bảo trì, sửa lỗi, nâng cấp. | Jira Service Desk |

<b>Câu 2.1 Về mô hình Thác nước. Phát biểu nào không đúng?</b> <br>
A. Mỗi giai đoạn phải được hoàn thành trước khi chuyển sang giai đoạn tiếp theo. <br>
<mark>B. Không phù hợp với các dự án có yêu cầu ổn định, đã được xác định rõ ràng ngay từ đầu.</mark> <br>
C. Đây là mô hình tuần tự, tuyến tính như dòng thác. <br>
D. Phù hợp với các dự án có yêu cầu ổn định.

> *Giải thích: Đáp án B sai vì mô hình Thác nước cực kỳ phù hợp với dự án ổn định, ít thay đổi.*

<b>Câu 2.2 Trong mô hình chữ V có đề cập tới 4 loại kiểm thử. Loại kiểm thử nào sau đây không đúng tên gọi?</b> <br>
A. Acceptance Testing <br>
<mark>B. Coding Testing</mark> <br>
C. System Testing <br>
D. Integration Testing

> *Giải thích: Trong V-Model, mức kiểm thử thấp nhất (tương ứng với Module Design) được gọi là **Unit Testing** (Kiểm thử đơn vị), không ai gọi là "Coding Testing".*

<b>Câu 2.3 Mô hình tiếp cận lặp gồm các công đoạn sau. Phát biểu nào không đúng?</b> <br>
A. Requirements <br>
<mark>B. Integration</mark> <br>
C. Design & Development <br>
D. Testing

> *Giải thích: Thông thường các pha chính là Requirements -> Design -> Dev -> Test. "Integration" thường là một hành động nằm trong pha Dev hoặc Test, ít khi đứng tên là một giai đoạn lớn ngang hàng với Requirements.*

<b>Câu 2.4 Trong mô hình Agile/Scrum. Phát biểu nào sau đây không đúng?</b> <br>
<mark>A. Scope: xác định phạm vi của biến</mark> <br>
B. Sprint: một chu kỳ phát triển ngắn (1-4 tuần). <br>
C. Product backlog: danh mục các chức năng của sản phẩm. <br>
D. Sprint backlog: danh mục chức năng của một sprint.

> *Giải thích: "Scope" trong quản lý dự án nghĩa là **Phạm vi dự án** (những việc cần làm, giới hạn công việc), hoàn toàn khác với khái niệm "phạm vi của biến" (variable scope) trong lập trình code.*

# Chương 3. Hệ thống quản lý phiên bản

## 1.6 Bài tập

<b>Câu 1.1 Các đặc điểm của hệ thống quản lý phiên bản cục bộ (Local VCS). Phát biểu nào không đúng?</b> <br>
A. Có thể thực hiện thủ công. <br>
B. Không hỗ trợ trong môi trường cộng tác nhiều người. <br>
C. Có thể dùng phần mềm để quản lý phiên bản kiểu cục bộ. <br>
<mark>D. Các phiên bản của dự án được lưu tập trung trên một máy server.</mark>

> *Giải thích: Hệ thống cục bộ chỉ lưu trên ổ cứng máy tính cá nhân. Việc lưu tập trung trên Server là đặc điểm của hệ thống Tập trung (Centralized VCS) hoặc Phân tán (Distributed VCS).*

<b>Câu 1.2 Các đặc điểm của hệ thống quản lý phiên bản tập trung (Centralized VCS). Phát biểu nào không đúng?</b> <br>
A. Các phiên bản của dự án được lưu tập trung trên máy server. <br>
<mark>B. Các máy client sẽ chứa tất cả các phiên bản của thư mục dự án cùng với lịch sử thay đổi.</mark> <br>
C. Máy client không thể tải phiên bản về khi server chết. <br>
D. Hỗ trợ làm việc cộng tác nhiều người.

> *Giải thích: Trong hệ thống tập trung (như SVN), Client thường chỉ tải về bản mới nhất (Snapshot) để làm việc. Việc Client chứa "tất cả lịch sử" là đặc điểm cốt lõi của hệ thống **Phân tán (Distributed)**.*

<b>Câu 1.3 Các đặc điểm của hệ thống quản lý phiên bản phân tán (Distributed VCS). Phát biểu nào không đúng?</b> <br>
A. Các máy client sẽ chứa toàn bộ các phiên bản của dự án, cùng lịch sử thay đổi. <br>
B. Hỗ trợ làm việc cộng tác nhiều người. <br>
C. Các phiên bản của dự án được lưu trên máy server (remote). <br>
<mark>D. Bạn không thể tạo và lưu phiên bản khi không có kết nối mạng tới máy server.</mark>

> *Giải thích: Đây là sức mạnh lớn nhất của hệ thống phân tán (như Git). Bạn hoàn toàn có thể commit (lưu phiên bản) ngay trên máy mình (Local Repo) mà không cần mạng Internet. Khi nào có mạng mới cần đẩy (push) lên server.*

<b>Câu 1.4 Tìm trang chủ của các phần mềm quản lý phiên bản.</b>

| Tên phần mềm | Trang chủ (Website) |
| :--- | :--- |
| **RCS** | [https://www.gnu.org/software/rcs/](https://www.gnu.org/software/rcs/) |
| **CVS** | [http://cvs.nongnu.org/](http://cvs.nongnu.org/) |
| **Subversion (SVN)** | [https://subversion.apache.org/](https://subversion.apache.org/) |
| **Git** | [https://git-scm.com/](https://git-scm.com/) |
| **Mercurial** | [https://www.mercurial-scm.org/](https://www.mercurial-scm.org/) |
| **Darcs** | [http://darcs.net/](http://darcs.net/) |

# Chương 4. Tổng quan về Git

## 2.4 Bài tập

<b>Bài tập 2.1 Thực hành các cài đặt trong bài học.</b>
*Link tài liệu thực hành: [Click here](https://drive.google.com/drive/folders/1g5N6bjw-Icr8atUKebA-df_4SeyS7HCV)*

<b>Câu 2.2 Lệnh nào được sử dụng để nhúng Git vào thư mục dự án?</b> <br>
<mark>A. git init</mark> <br>
B. git --init <br>
C. git initialize <br>
D. git embed

> *Giải thích: `init` là viết tắt của **initialize** (khởi tạo). Lệnh này sẽ sinh ra một thư mục ẩn tên là `.git` trong dự án. Nếu không có thư mục này, Git sẽ không thể theo dõi dự án.*

<b>Câu 2.3 Lệnh nào sử dụng để kiểm tra trên máy tính đã có phần mềm Git hay chưa?</b> <br>
A. git ver <br>
B. git version <br>
<mark>C. git -v</mark> <br>
D. git --ver

> *Giải thích: Cú pháp chuẩn để kiểm tra phiên bản là `git --version` (đầy đủ) hoặc `git -v` (viết tắt). Các lệnh còn lại không đúng chuẩn cú pháp lệnh của Git.*

<b>Câu 2.4 Trong Git, kho lưu trữ (repo, repository) là gì?</b> <br>
A. Là thư mục dự án. <br>
B. Là thư mục dự án đã được nhúng Git. <br>
C. Là thư mục cài đặt phần mềm Git. <br>
<mark>D. Là thư mục .git (trong thư mục dự án).</mark>

> *Giải thích: Đây là điểm quan trọng nhất. Thư mục bạn nhìn thấy code chỉ là "Thư mục làm việc" (Working Directory). Còn **Kho lưu trữ (Repository)** thực sự chính là thư mục ẩn **`.git`** - nơi chứa toàn bộ cơ sở dữ liệu và lịch sử thay đổi của dự án.*

# Chương 5. Cấu hình định danh người dùng

## 3.4 Bài tập và câu hỏi

<b>Bài tập 3.1: Bài tập tình huống “Quản lý cấu hình Git cho nhiều dự án”</b>

> **Yêu cầu:** Cấu hình để dự án công ty (TeoTech) dùng email công ty, dự án cá nhân (VienVong) dùng email cá nhân.

**Giải pháp thực hiện:**

1.  **Cấu hình chung (Global) cho tài khoản cá nhân:**
    ```bash
    git config --global user.name "Nguyen Van Teo"
    git config --global user.email "nvteo@gmail.com"
    ```
    *(Dùng cho mọi dự án mặc định).*

2.  **Cấu hình riêng (Local) cho dự án công ty:**
    * Di chuyển vào thư mục dự án công ty: `cd TeoTechProject`
    * Chạy lệnh config (không có --global):
    ```bash
    git config user.name "Nguyen Van Teo"
    git config user.email "nvteo@teotech.com"
    ```

**Kết quả:**
* Dự án `VienVongProject`: Dùng email gmail (do lấy từ Global).
* Dự án `TeoTechProject`: Dùng email teotech (do Local ghi đè Global).

<b>Câu 3.2 Phạm vi cấu hình định danh trong Git là gì? Phát biểu nào sau đây không đúng?</b> <br>
A. Phạm vi system áp dụng cho tất cả người dùng và kho lưu trữ trên hệ thống. <br>
B. Phạm vi global áp dụng cho tài khoản người dùng hiện tại và tất cả kho lưu trữ. <br>
<mark>C. Phạm vi local áp dụng cho một kho lưu trữ cụ thể và có độ ưu tiên thấp nhất.</mark> <br>
D. Phạm vi local áp dụng cho một kho lưu trữ cụ thể và có độ ưu tiên cao nhất.

> *Giải thích: Trong Git, cấu hình **Local (Cục bộ)** luôn có độ ưu tiên **CAO NHẤT**. Thứ tự ưu tiên đúng là: Local > Global > System.*

# Chương 6. Các khu vực làm việc của Git

