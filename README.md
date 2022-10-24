# voting
Python implementation of an e-voting system using Paillier homomorphic encryption.

Yêu Cầu : Python 3.x

Các bước chạy chương trình

Bước 1: Sửa file config.py nếu cần thiết

Bước 2: Tạo khoá và data:
             		 python voting_authority.py

  chọn 1 để để tạo khoá và cử chi 

	mặc định sẽ có 3 cử chi được được là : Voter1 -> Voter3 và id tương ứng từ 1 -> 3 

	các cử chi được ghi vào voter.txt

	các khoá được lưu vào file : public.txt và private.txt
	
Bước 3: Bỏ phiếu:
					python vote.py

	Nhập tên và id cử chi để kiểm tra nếu hợp lệ sẽ được bỏ phiếu

	Mặc định từ 1 - 4

	Sau khi bỏ phiếu chương trình sẽ trả về 1 vote_id để theo dõi trong bảng thông báo

	Dữ liệu phiếu bầu được mã hoá và lưu vào file encrypted_vote.txt

	Chương trình sẽ hỏi bỏ phiéu lại vơi cử chi khác không. Nếu tất cả cử chi đã bỏ phiếu thì sẽ kết thúc phiên bầu cử và chương trình tự động dừng
	
	dùng : python bulletin_board.py để kiểm tra trạng trái phiếu bầu dựa vào vote-id được trả về khi bầu cử
  
	dùng : python vote_end.py để kết thúc phiên bầu cử
	
Bước 3: Mã hoá kết quả:
				python homomorphic_server.py để mã tất cả bản mã của phiếu bầu và lưu vào file homomorphic_vote.txt

				chỉ thực hiện được khi phiên bầu cử kết thúc

Bước 4: Giải mã và xem kết quả bầu cử:

				python voting_authority.py

				chọn 2 để giải mã file homomorphic_vote.txt vài in kết quả ra màn hình
