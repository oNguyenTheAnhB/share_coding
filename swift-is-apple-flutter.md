# SwiftUI là Apple's Flutter

![](https://miro.medium.com/max/700/1*kW3vK1LpYOyG0JA12urVAQ.png)

Đó là một năm quan trọng đối với Swift và SwiftUI, bắt đầu bằng các thông báo của Apple tại WWDC và đỉnh điểm là việc phát hành Swift 5.3 trong tuần này. Trong số rất nhiều tính năng mới thú vị "[Swift.org](https://swift.org/blog/swift-5-3-released/)" đã thông báo rằng Swift “đáng chú ý là hỗ trợ thêm cho Windows và các bản phân phối Linux bổ sung”.

Làm việc tại một công ty đang xây dựng ứng dụng cho các nền tảng của Apple, Android và Windows rõ ràng là sự quan tâm của tôi. Hỗ trợ của Windows thực sự có nghĩa là gì? Và tại sao không có tên trong danh sách các bản phân phối Linux?

Trước khi cho bạn biết điều mà tôi nghĩ câu trả lời cho những câu hỏi đó, chúng ta hãy cùng nhìn lại lịch sử của chén thánh của bất kỳ lập trình viên nào, Write Once, Run Anywhere.

### Mơ một giấc mơ bất khả thi

Lần đầu tiên tôi nhớ lại khi nghe thấy tiếng còi báo động của Write Once, Run Anywhere (WORA) là từ cộng đồng Java vào những năm 90. Đó là một màn chào sân quyến rũ và vẫn còn. Và Java không phải là người duy nhất thực hiện lời hứa này. Flash và Flash AIR đã làm, cùng với Mozilla’s XUL Runner và những người khác. Nhưng thực tế của những giải pháp này luôn không như những lời hứa hẹn.

Việc thêm một lớp phát triển trên hệ điều hành của bên thứ 3 sẽ làm tăng thêm độ phức tạp rất lớn, cả từ quan điểm kỹ thuật và từ quan điểm giao diện người dùng. Người dùng của các nền tảng được hỗ trợ sẽ có ứng dụng chậm hơn bình thường, với giao diện người dùng lạ lẫm không tuân thủ các tiêu chuẩn của nền tảng. Bây giờ nó là Viết một lần, Săn lỗi mọi nơi để các nhà phát triển ngày càng chuyển sang HTML5 để giải quyết vấn đề đa nền tảng.

Nhưng như mọi khi, những ý tưởng này không bao giờ thực sự biến mất. Facebook đã đi tiên phong trong một cách tiếp cận giống như nhà phát triển web đối với các ứng dụng gốc với React Native và Microsoft đã phát triển lĩnh vực này với Xamarin.

Nhưng dự án đang được chú ý nhất những ngày này là Flutter. [Bài báo này](https://medium.com/swlh/flutter-and-fuchsia-the-death-of-react-android-a34f6d12bb82) từ năm ngoái giới thiệu tốt về Flutter và thậm chí còn đưa ra lời hứa!

![](https://miro.medium.com/max/700/1*T9oahKiF_vtwhqH40uKYxQ.png)

> Flutter is a framework allowing you to build cross-platform apps. It started off as a toolkit allowing you to build consistent apps for both IOS and Android. Now … Google released a technical preview for flutter web, allowing you to run the same application natively on Mobile, Web, Desktop and even embedded devices. Using Google’s UI that has been ported to all the listed platforms, you can write the code once and run it everywhere!

Rõ ràng là tại sao Google muốn khung ứng dụng đa nền tảng của riêng mình, họ là một công ty dịch vụ. Nhưng đó không phải là những gì Apple được cho là sẽ trở thành?

### Swift đã thay đổi

Apple luôn được biết đến như một nền tảng đóng có tường bao quanh, và vì lý do chính đáng. Cho dù đó là một điều tốt hay không là một cuộc tranh luận riêng biệt. Tuy nhiên, Apple có các ứng dụng cho các nền tảng khác và đã và đang mở rộng về mặt đó. Lợi ích của việc hỗ trợ các nền tảng khác đã trở nên rõ ràng khi Apple phát hành iTunes cho Windows. Doanh số của iPod tăng vọt và tạo tiền đề cho iPhone. Điều cũng trở nên rõ ràng là Apple gần như không tốt trong việc tạo ra phần mềm dễ sử dụng trên các nền tảng khác.

Trong những năm tiếp theo, họ không thực sự tốt lên nhiều. Điều đó dường như đang thay đổi với trục quay gần đây của họ trên AppleTV. Cho đến hôm nay, điều tốt nhất tôi có thể xác định là Apple hiện đang cung cấp Apple Music, AppleTV và iCloud dưới dạng các ứng dụng gốc trên nền tảng của bên thứ ba. Mặc dù họ đã mở rộng các phiên bản dựa trên web của một số ứng dụng của họ, nhưng tôi không tin rằng Apple cho rằng đó là tương lai.

![](https://miro.medium.com/max/700/1*ZrQoPdx_up6TDq6jdxQHOg.png)

Nếu Apple thực sự muốn trở thành một công ty dịch vụ, thì họ có cần những dịch vụ đó trên nhiều nền tảng nhất có thể không? Ngoài ra, đây là 5 ứng dụng hoặc dịch vụ khác của Apple cũng sẽ được hưởng lợi khi có sẵn trên các nền tảng khác.

* Messages
* Books
* Maps
* News
* Home

Vì vậy, rõ ràng là Apple cần có nhiều ứng dụng hơn của họ trên các nền tảng khác giống như Google và Microsoft. Nhưng đâu sẽ là cách tiếp cận tốt nhất cho Apple? Thuê lập trình viên quen thuộc với từng nền tảng? Hay tạo giải pháp của bạn cho các nền tảng đó?

### Swift mọi nơi

Ngay từ đầu, Apple đã nói rằng họ muốn ngôn ngữ Swift có mặt ở khắp mọi nơi. Hầu hết các nhà phát triển không tin họ, nhưng hành động của Apple dường như đã cam kết với con đường đó. Và trong khi SwiftUI và Swift không giống nhau, tôi tin rằng chúng ta đang thấy những nền tảng được đặt ra để sự kết hợp Swift / SwiftUI trở thành một giải pháp đa nền tảng thực sự.

Hãy quay lại ghi chú đó về các hệ điều hành được hỗ trợ bổ sung trong Swift 5.3, Windows và các bản phân phối Linux bổ sung. Điều làm tôi ngạc nhiên là tại sao không đặt tên cho một số bản phân phối Linux? Nếu Swift đến với các bản phân phối đã biết như Fedora hoặc Mint thì liệu chúng có được liệt kê không? Sau đó, nó nhấp vào. Hầu hết tất cả các smartTV hiện đại đều chạy phiên bản Linux. Và Apple đã làm gì? Phát hành ứng dụng AppleTV trên LG, Samsung và các TV thông minh khác.

Mặc dù tôi không biết về cách Apple mã hóa các ứng dụng đó cho các nền tảng TV, tôi đoán rằng đó là việc triển khai nội bộ của Swift và SwiftUI chạy trên Linux (lưu ý rằng Android dựa trên Linux). Ngoài ra, bước đầu tiên để đưa sự kết hợp của Swift và SwiftUI vào Windows là việc phát hành Swift trên Windows trong phiên bản 5.3.

Vì vậy, có thể không lâu nữa cho đến khi Apple có thể phát triển các ứng dụng với một cơ sở mã có thể được triển khai cho không chỉ các nền tảng của riêng họ mà còn cho Windows, Android, TV thông minh và hơn thế nữa. Câu hỏi rõ ràng là họ sẽ phát hành công nghệ này cho các nhà phát triển bên ngoài? Tôi tin rằng câu trả lời là có.

Tại sao? Bởi vì Apple đã thấy các ứng dụng Electron và điều đó có ý nghĩa như thế nào đối với trải nghiệm gốc. Nếu sắp có một khung nền tảng chéo cuối cùng giải quyết được công thức WORA, bạn có thể cá rằng Apple muốn đứng sau nó. Bằng cách đó, Apple có ảnh hưởng nhiều hơn đến các công nghệ được điều chỉnh. Giữ một công cụ dành cho nhà phát triển đa nền tảng thực sự cho riêng mình sẽ chỉ khuyến khích các nhà phát triển chuyển sang Flutter hoặc thứ gì đó tương tự.

Với sự bùng nổ của các thiết bị tiêu dùng và việc chuyển sang đăng ký, Apple và các gã khổng lồ công nghệ khác phải cung cấp dịch vụ của họ cho các nền tảng cạnh tranh. Đối với tôi, dường như cách duy nhất để làm điều đó và không phụ lòng đối thủ cạnh tranh của bạn là có giải pháp duy nhất của bạn. Trong trường hợp của Apple, đó sẽ là Swift và SwiftUI.

[Link](https://medium.com/swlh/swiftui-is-apples-flutter-184d16001bd9)