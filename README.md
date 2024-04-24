# LEARNING GIT
GIT - Distributed Version Control System là một hệ thống quản lý và chia sẽ source code phổ biến nhất hiện nay.
GIT cung cấp cho developer 1 kho lưu trữ chứa tất cả các file của dự án và ghi lại toàn bộ lịch sử thay đổi trong quá trình phát triển dự án
### Hoàn tác trong GIT
Có rất nhiều cách để hoàn tác thay đổi trong Git. Và cũng tương tự như commit, hủy thay đổi trong Git có cả thành phần bậc thấp (tạm thời lưu trữ một số tệp hoặc đoạn độc lập) và thành phần bậc cao (cách mà các thay đổi thực sự bị hủy). <br /> 

Có 2 cách cơ bản để hủy thay đổi trong Git -- một là dùng git reset, hai là dùng git revert.

- Git reset hoàn tác bằng cách chuyển tham chiếu của nhánh ngược lên commit cũ hơn. Có thể hiểu nó như kiểu "viết lại lịch sử;" 
git reset sẽ dịch chuyển nhánh lên trên như thể commit chưa bao giờ được tạo ra vậy.
    >  Git chuyển tham chiếu của main trở lại, bây giờ kho lưu trữ trông như thể commit trước đó chưa bảo giờ xảy ra

- Git revert có thể hoàn tác và chia sẻ hoàn tác đó với người khác
    > Lúc này một commit mới được tạo ra(‘) thả vào bên dưới commit mà ta muốn hoàn tác. - Đó là bởi vì commit mới  này có chứa những thay đổi hoàn toàn ngược lại với những thay đổi trong commit trước đó và ta có thể đẩy thay đổi này lên và chia sẽ với người khác

### Merge
Hợp nhất code của commit mới nhất vào nhánh mà mình muốn merge.

Ví dụ
```
A---B---C  (master)
            \
             D---E---F  (feature)

// sau khi merge

A---B---C---M  (master)
    \       /
     D---E---F  (feature)
```
> M là commit merge mới mà Git tự động tạo ra để kết hợp các thay đổi từ nhánh feature vào nhánh master.
### Cherry-pick and Rebase
1. Cherry-pick

Git cherry-pick sẽ copy 1 hoặc 1 loạt commit trên 1 nhánh nào đó áp dụng vào nhánh hiện tại. (xuống dưới vị trí hiện tại của bạn - HEAD)

Ví dụ
```
master:      A---B---C---D
                            \
feature/crawl_video_links:    E---F---G

// sau khi cherry-pick

master:      A---B---C---D---F'---G'
```
>Lệnh git cherry-pick để chọn một hoặc nhiều commit từ một nhánh khác và áp dụng chúng vào nhánh hiện tại của bạn, thứ tự commit trên nhánh hiện tại sẽ được cập nhật sao cho các commit được chọn sẽ được áp dụng sau commit mới nhất của nhánh hiện tại.
2. Rebase

Git Rebase cấu trúc lại lịch sử commit, có nghĩa là nó merge code từ mốt nhánh vào nhánh khác. 

Ví dụ
```
master:      A---B---C---D
                 \
feature/crawl_video_links:  E---F---G

// sau khi rebase

master:      A---B---C---D
                            \
feature/crawl_video_links:    E'---F'---G'
```
>Lệnh git rebase master trên nhánh feature/crawl_video_links, Git sẽ di chuyển tất cả các commit trên nhánh feature/crawl_video_links một cách tuần tự lên trên commit mới nhất trên nhánh master. Điều này có nghĩa là Git sẽ di chuyển từng commit một, bắt đầu từ commit đầu tiên của feature/crawl_video_links đến commit cuối cùng trên nhánh feature/crawl_video_links, và áp dụng chúng trên commit mới nhất trên nhánh master.