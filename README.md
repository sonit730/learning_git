# LEARNING GIT

### Hoàn tác trong GIT
Có rất nhiều cách để hoàn tác thay đổi trong Git. Và cũng tương tự như commit, hủy thay đổi trong Git có cả thành phần bậc thấp (tạm thời lưu trữ một số tệp hoặc đoạn độc lập) và thành phần bậc cao (cách mà các thay đổi thực sự bị hủy). <br /> 

Có 2 cách cơ bản để hủy thay đổi trong Git -- một là dùng git reset, hai là dùng git revert.

- Git reset hoàn tác bằng cách chuyển tham chiếu của nhánh ngược lên commit cũ hơn. Có thể hiểu nó như kiểu "viết lại lịch sử;" 
git reset sẽ dịch chuyển nhánh lên trên như thể commit chưa bao giờ được tạo ra vậy.
    >  Git chuyển tham chiếu của main trở lại, bây giờ kho lưu trữ trông như thể commit trước đó chưa bảo giờ xảy ra

- Git reset có thể hoàn tác và chia sẻ hoàn tác đó với người khác
    > Lúc này một commit mới được tạo ra(‘) thả vào bên dưới commit mà ta muốn hoàn tác. - Đó là bởi vì commit mới  này có chứa những thay đổi hoàn toàn ngược lại với những thay đổi trong commit trước đó và ta có thể đẩy thay đổi này lên và chia sẽ với người khác

### Cherry-pick