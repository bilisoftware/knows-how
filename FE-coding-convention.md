# FE coding convention


Một phần mềm khi trong quá trình phát triển thường dành phần lớn thời gian từ 40-80% để duy trì và bảo trì phần mềm, vì vậy công việc của một developer không chỉ là viết code để xây dựng ứng dụng đó, mà còn phải tuân thủ theo các quy định code (coding convention) để giúp những dòng code mình tạo ra giúp người sau dễ đọc, dễ bảo trì và có thể tái sử dụng, vì lẽ đó sau đây là một số các coding convention mà Bili Devs nên tuân thủ:<br />
## Import rules: <br />
việc import phải được sắp xếp theo thứ tự sau: <br />
```
import React from 'react'
import Thư Viện; ví dụ: import {Box} from 'native-base'
import * as ''; ví dụ: import * as lodash from 'lodash"
import file components; ví dụ: import Header from './Header'
```

## File structures <br />
```
└── /Tên module
  ├── /index.tsx - file container chứa toàn bộ logic và tập trung các components
  ├── /components - folder with reusable components như Header, Footer, Content
  ├── /services.ts - chứa các hàm call api (query function - gọi theo react query)
  ├── /slice.ts - redux reducer
  ├── /utils - utilities, helpers, constants.
  ├── interface.ts define type for constants, data
  └── hooks - folder with custom hooks use for components
  └──common ( nếu có các component tái sử dụng được trong cả module đó thì di chuyển vào đây )
  ```
  ## Naming convention:
  ``` 
File name luôn được đặt theo kiểu PascalCase ví dụ: RegisterForm
Tên biến thì tuân thủ theo camelCase: formValue, onChange,…
Nếu tên biến type boolean thì prefix sẽ là has, is ví dụ: isTrue, hasRegistered
Đặt tên hàm phải bắt đầu bằng động từ: handlePress, doSomething,…
```
### Note:
- Trong một folder luôn phải có file index.tsx (container) để handle toàn bộ logic và tập hợp các component lại với nhau <br />
- Khi làm một màn hình, luôn phải tách nhỏ các bộ phận của màn hình đó ra như là: Header, Content, Footer. Việc này sẽ giúp code clean và dễ tái sử dụng lại
- Không được dùng các giá trị đơn lẻ để so sánh, truyền lên gọi api,… mà phải đặt thành constant để nhỡ sau này có thay đổi thì chỉ việc thay đổi 1 chỗ, tránh bị bỏ sót gây ra bug
- Các điều kiện khi có 2 điều kiện đồng thời trở lên phải được đặt thành constant
- Mỗi một cụm logic phải được cách ra thêm 1 dòng để đảm bảo rằng chúng đang cùng handle một hành động
- Luôn sử dụng optional chaining ‘?.’ để giảm thiểu undefined data gây ra crash app
- Khi nhận props vào một component sử dụng destructuring để lấy giá trị
- Khi tạo biến không sử dụng var
- Sử dụng arrow function để code clean
- Đặt comment code giải thích ‘Tại Sao’ lại handle như vậy ở những chỗ dễ gây confuse cho người sau
- Thống nhất khi import lodash thì sẽ là import lodash from ‘lodash’
- Bỏ console.log trước khi commit code (cái này trong dự án có thể cài tool để nhắc)
- Commit message phải có nghĩa, rõ ràng code trong commit đó là làm gì, ví dụ implement login ui, mapping api for login screen, fix bug ticket ‘id ticket’,… không được đặt chung chung như fix bug,…
- Validate form phải sử dụng React Hook Form không validate manual 
- Coding UI sử dụng Native Base, Chakra Ui, Material Ui
- Không được tự ý cài thêm lib khi chưa có sự đồng ý từ leader
