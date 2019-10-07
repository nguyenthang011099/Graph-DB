# Graph-DB
in class
Bài Tập 1:
Nhóm 2 : 5 thành viên
Đề bài
Tìm Hiểu về GraphDB

I, Tổng quan về graph database
Như tên gọi thì graph databse là một kiểu cơ sở dữ liệu đồ thị, một tập các đối tượng gọi là đỉnh nối với nhau bởi các cạnh. Thông thường, đồ thị được vẽ dưới dạng một tập các điểm (đỉnh, nút) nối với nhau bởi các đoạn thẳng (cạnh). Tùy theo ứng dụng mà một số cạnh có thể có hướng.
Chúng ta đã quen với cách biểu diễn theo cơ sở dữ liệu quan hệ truyền thống, nhưng với những bài toán cần nhiều quan hệ việc sử hệ để lưu trữ không phải là một giải pháp hay vì :
    • Việc biểu diễn quan hệ dưới dạng bảng không phải là một cách làm trực quan.
    • Các phép join thường tốn rất nhiều chi phí
Trong Graph Database quan hệ là những liên kết trực tiếp giữa các thực thể (các đỉnh). Do đó graph database giúp trả lời rất nhiều câu hỏi liên quan đến truy vấn dữ liệu một cách hiệu quả.
Trong graph database có 3 khái niệm cơ bản quan trọng nhất :
    • Node: chính là các thực thế hay các đối tượng, graph ko quan tâm đến kiểu dữ liệu của các thực thể.
    • Properties: là các thuộc tính, được đặt tên sao cho nó liên quan nhất đến các node. Ví dụ: nếu ta đặt 1 node là xe máy thì ta sẽ liên tưởng đến các thuộc tính phân khối...
    • Edges: là các cạnh nối các node, có thể coi chúng là quan hệ giữa các đối tượng và tạo lên các cấu trúc dữ liệu. Một điều quan trọng mà ta cần hiểu được là xác định được node đến và node đi để xác định đúng mối quan hệ giữa chúng
Với những nơi có dữ liệu liên kết nhiều: ví dụ của mạng xã hội, các ứng dụng gợi ý nghe nhạc, xem phim, các phầm mềm quản lý xí nghiệp nhà máy thì Graph Database sẽ là 1 lựa chọn tốt nhất.

II, Cách cài dặt:
Tham khảo trên mạng có nhiều cách cài đănt nên phần đó mình không nói ở đây

 III, Thiết kế mô hình dữ liệu

Về cơ bản, việc thiết kế một CSDL đồ thị cũng tương tự như khi ta thiết kế CSDL quan hệ và mô hình đồ thị thuộc tính (Graph Property Model) với sơ đồ thực thể kết hợp (ERD) cũng khá giống nhau, cụ thể, ta cần có các thực thể (đối cới CSDL quan hệ), các nút (đối với CSDL đồ thị) và các mối quan hệ giữa chúng. Diểm khác biệt lớn nhất là khi hiện thực, các thực thế của CSDL quan hệ sẽ là một bảng chứa tập các record (thực thể cụ thể), các mối quan hệ có thể thành thực thể kết hợp. Với CSDL đồ thị, việc thiết kế với hiện thực gần như là giống nhau. Hay nói cách khác, với CSDL đồ thị, thiết kế như thế nào sẽ được hiện thực đúng như vậy. Để thiết kế một cơ sở dữ liệu đồ thị, ta cần chú ý đến các kỹ thuật sau:
    • Sử dụng các câu hỏi đối với dữ liệu từ những câu chuyện của người dùng hay để xác định các thực thể cũng như các mối quan hệ.
    • Sử dụng các nút để đại diện cho các thực thể – những gì nằm trong mối quan tâm của vấn đề.
    • Sử dụng các mối quan hệ để thể hiện sự kết nối giữa các thực thể và để thiết lập các bối cảnh ngữ nghĩa cho mỗi thực thể, từ đó cấu trúc miền vấn đề.
    • Sử dụng các thuộc tính nút để đại diện cho các tính chất của thực thể, và cả bất kỳ siêu dữ liệu thực thể cần thiết nào, như nhãn thời gian, phiên bản …
    • Sử dụng các thuộc tính của các mối quan hệ để thể hiện tính quan trọng, chất lượng của một mối quan hệ và cả các siêu dữ liệu quan hệ cần thiết khác như nhãn thời gian, phiên bản …
    • Mô hình hóa sự kiện như là các nút trong trường hợp hai hoặc nhiều thực thể khác nhau tương tác trong cùng một khoảng thời gian thì một sự kiện xuất hiện. Chúng ta có thể biểu diễn những sự kiện này bằng các node riêng, và kết nối với các thực thể tham gia sự kiện đó.
    • Các kiểu giá trị phức tạp đại diện là các nút. Kiểu dữ liệu phức tạp là những kiểu dữ liệu có hơn một trường hoặc thuộc tính. Ví dụ như địa chỉ, địa chỉ có thể bao gồm quốc gia, số nhà, đường phố … Đối với những kiểu giá trị phức tạp thế này, cách tốt nhất là biểu diễn chúng bằng các node riêng biệt.


IV, Truy xuất dữ liệu
Truy xuất theo SPARQL API
SPARQL, là viết tắt của Giao thức SPARQL và Ngôn ngữ Truy vấn RDF bằng tiếng Anh, “SPARQL Protocol And RDF Query Language”, cho phép những người sử dụng truy vấn thông tin từ các cơ sở dữ liệu hoặc bất kỳ nguồn dữ liệu nào có thể được ánh xạ tới RDF.
Tiêu chuẩn SPARQL được W3C thiết kế và phê chuẩn và giúp những người sử dụng và những người phát triển tập trung vào những gì họ muốn biết thay vì cách mà cơ sở dữ liệu được tổ chức.
SPARQL so với SQL
Hệt như SQL cho phép người sử dụng truy xuất và sửa đổi dữ liệu trong cơ sở dữ liệu quan hệ, SPARQL cung cấp chức năng y hệt cho các cơ sở dữ liệu đồ họa NoSQL như GraphDB.
Hơn nữa, một truy vấn SPARQL cũng có thể được thực thi trong bất kỳ cơ sở dữ liệu nào mà có thể được xem như RDF thông qua phần mềm trung gian (middleware). Ví dụ, cơ sở dữ liệu quan hệ có thể được yêu cầu truy vấn với SPARQL bằng việc sử dụng phần mềm ánh xạ cơ sở dữ liệu quan hệ sang RDF - RDB2RDF (Relational Database to RDF).
Đây là những gì làm cho SPARQL trở thành ngôn ngữ mạnh mạnh để tính toán, lọc, tổng hợp và có chức năng truy vấn tiếp (subquery).
Tương phản với SQL, các truy vấn SPARQL không bị ràng buộc phải làm việc bên trong một cơ sở dữ liệu: Các truy vấn liên đoàn (Federated queries) có thể truy cập nhiều kho dữ liệu (các điểm cuối). Hệ quả là, SPARQL vượt qua được các ràng buộc do sự tìm kiếm cục bộ đặt ra.
Sức mạnh của SPARQL cùng với sự mềm dẻo của RDF có thể dẫn tới các chi phí phát triển thấp hơn khi mà việc pha trộn các kết quả từ nhiều nguồn dữ liệu là dễ dàng hơn.
Các lựa chọn thiết kế đó - xúc tác cho các truy vấn đối với các nguồn phân tán về dữ liệu không thống nhất, là không ngẫu nhiên. SPARQL được thiết kế để xúc tác cho Dữ liệu Liên kết (Linked Data) cho Web Ngữ nghĩa (Semantic Web). Mục tiêu của nó là để hỗ trợ cho mọi người làm giàu dữ liệu của họ bằng việc liên kết nó với các tài nguyên ngữ nghĩa toàn cầu khác, cũng như việc chia sẻ, pha trộn, và sử dụng lại dữ liệu theo một cách thức có ý nghĩa hơn.
SPARQL từ bên trong
SPARQL coi dữ liệu của bạn như là đồ họa (graph) có định hướng, được gắn nhãn, điều đó được trình bày nội bộ bên trong như là bộ 3 gồm chủ ngữ, vị ngữ và bổ ngữ (subject, predicate and object).
Một cách tương ứng, truy vấn SPARQL gồm một tập hợp 3 mẫu theo đó từng yếu tố (chủ ngữ, vị ngữ và bổ ngữ) có thể là một biến (wildcard). Các giải pháp với các biến sau đó được thấy bằng việc khớp các mẫu trong truy vấn đó với bộ 3 trong tập hợp dữ liệu.
SPARQL có 4 dạng truy vấn. Nó có thể được sử dụng để:
    1. ASK (Hỏi) liệu có ít nhất 1 sự trùng khớp mẫu truy vấn trong dữ liệu đồ họa RDF hay không;
    2. SELECT (Chọn) tất cả hoặc vài sự trùng khớp đó ở dạng bảng (bao gồm sự tổng hợp, làm mẫu và phân trang qua OFFSET và LIMIT);
    3. CONSTRUCT (Xây dựng) đồ họa RDF bằng việc thay thế các biến trong các trùng khớp đó trong một tập hợp các mẫu template bộ 3 đó; hoặc
    4. DESCRIBE (Mô tả) các trùng khớp được tìm thấy đó bằng việc xây dựng đồ học RDF thích hợp.
Các cơ sở dữ liệu đồ họa ngữ nghĩa hàng đầu có hỗ trợ SPARQL, gồm GraphDB Free, đặc trưng cho các trình soạn thảo SPARQL trực quan với các tính năng tự động hoàn chỉnh, trình khai phá (explorer) và nhiều chức năng hơn, chúng chỉ dẫn cho các nhà khoa học về dữ liệu trong việc xây dựng các truy vấn SPARQL mạnh.
Sức mạnh của SPARQL trong ví dụ
Điểm mạnh nhất của SPARQL là điều hướng các mối quan hệ (navigating relations) trong dữ liệu đồ họa RDF thông qua việc khớp mẫu đồ họa, nơi mà các mẫu đơn giản có thể được kết hợp trong các mẫu đồ họa phức tạp hơn mà khai thác các mối quan hệ tỉ mỉ hơn trong các dữ liệu đó.
Các mối quan hệ như vậy có thể được khai thác bằng việc sử dụng các mẫu cơ bản, các kết nối mẫu, các liên minh, bằng việc thêm vào các mẫu tùy chọn mà có thể mở rộng thông tin về các giải pháp được tìm thấy, … Hơn nữa, các con đường đúng đắn cho phép sự kết hợp tuần tự (xếp chuỗi), sự kết hợp song song (xen kẽ), sự lặp đi lặp lại (Kleene star), sự nghịch đảo, …
Mẫu đồ họa cơ bản gồm bộ 3 theo đó từng yếu tố (chủ ngữ, vị ngữ và bổ ngữ) có thể là một biến (wildcard).



