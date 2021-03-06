# BoostCourse

### [BoostCourse-iOS](http://www.edwith.org/boostcourse-ios)

### 오리엔테이션
- [x] __01. Hello! iOS Developer!__
- [x] __02. 개발 이야기__
- [x] __03. 코스 시작에 앞서...__
- [x] __04. 시작합니다!__
- - -
### 1. 음원 재생기 애플리케이션 (18.05.05 완료)
- [x] __0.Hello!__
- [x] __1. 시작 그리고 Xcode__
- [x] __2. 애플리케이션 만들기__
    * _인터페이스 빌더의 객체를 코드와 연결(IBOutlet)_
        ```
        * 코드로 먼저 IBOutlet을 생성한 후 인터페이스 빌더의 Outlet Inspector를 통해 연결
        * 코드로 먼저 IBOutlet을 생성한 후 인터페이스 빌더에서 View Controller 우클릭 후 팝업에서 연결
        * 인터페이스 빌더에서 코드로 끌어당겨 연결
    * _인터페이스 빌더의 객체에서 발생한 액션을 코드의 메서드와 연결_
        ```
        * 코드로 먼저 IBAction을 생성한 후 인터페이스 빌더의 Outlet Inspector를 통해 연결
        * 코드로 먼저 IBAction을 생성한 후 인터페이스 빌더에서 View Controller 우클릭 후 팝업에서 연결
        * 인터페이스 빌더에서 코드로 끌어당겨 연결
- [x] __3. Foundation과 UIKit 그리고 Cocoa Touch__
- [x] __4. 오토 레이아웃__
    ```
    * 인터페이스 빌더에서 오토레이아웃 구현하기
        1. 뷰와 뷰 사이에 ctrl 키 누르고 드래그하는 방식
        2. 스택, 정렬, 핀 그리고 리졸브를 사용하는 방식
        3. 인터페이스 빌더가 제약 설정하는 방식
- [x] __5. iOS의 View 체계__
- [x] __6. MVC__
    * Model-View-Controller
        ```
        * Model : 애플리케이션과 관련된 데이터를 캡슐화하고, 해당 데이터를 조작하고 처리하는 로직과 계산을 정의
        * View : 애플리케이션 내에서 사용자가 볼 수 있는 객체
        * Controller : 하나 이상의 애플리케이션 뷰 객체와 하나 이상의 모델 객체 사이의 코디네이터 또는 중개자 역할
- [x] __7. Apple Developer Documentation__
    * Doumentation 읽는 연습할 것!
- [x] __8. Summary__
- - -
### 2. 회원가입 화면 구현 (18.05.10 완료)
- [x] __0. Hello!__
- [x] __1. Human Interface Guidelines__
- [x] __2. 화면의 전환__
    * Modal : 이목을 집중해야 하는 화면을 다른 화면 위로 띄워(Presenting) 표현하는 방식 (= Android의 Intent, Activity)
        * 뷰 컨트롤러를 화면 상에 나타내는 방법 2가지(컨테이너 뷰 컨트롤러에 임베드, 프레젠테이션)
            ```
            * Fuil-Screen Presentaion Style : 화면 전체를 덮으며, 아래의(underlying) 기본 콘텐츠와 상호작용을 방지
            * The Popover Style : 뷰 컨트롤러를 팝오버뷰로 나타냄(iPad만 지원)
            * The Current Context Styles : 아래 뷰 컨트롤러의 콘텐츠 영역에 콘텐츠를 올리는 형태
            * Custom Presentation Styles : 정의한 커스텀 스타일을 사용하여 뷰 컨트롤러를 표시
            * Transition Styles : 뷰 컨트롤러를 표시하는데 사용하는 애니메이션 유형을 결정
- [x] __3. 뷰의 상태변화 감지__
    * 뷰의 상태변화 메서드
        * _func viewDidLoad()_
            ```
            - 뷰 계층이 메모리에 로드된 직후 호출되는 메서드
            - 뷰의 추가적인 초기화 작업을 하기 좋은 시점
            - 메모리에 처음 로딩 될때 1회 호출되는 메서드로, 메모리 경고로 뷰가 사라지지 않는 이상 다시 호출되지 않음
            - (= Android의 onCreate() )
        * _func viewWillAppear(_ _animated: Bool)_
            ```
            - 뷰가 뷰 계층에 추가되고 화면이 표시되기 직전에 호출되는 메서드
            - 뷰의 추가적인 초기화 작업을 하기 좋은 시점
            - 다른 뷰로 이동했다가 되돌아오면 재호출되는 메서드로, 화면이 나타날때마다 수행해야하는 작업을 하기 좋은 시점
            - (= Android의 onResume() )
        * _func viewDidAppear(_ _animated: Bool)_
            ```
            - 뷰가 뷰 계층에 추가되어 화면이 표시되면 호출되는 메서드
            - 뷰를 나타내는 것과 관련된 추가적인 작업을 하기 좋은 시점
            - (= Android의 onStart() )
        * _func viewWillDisappear(_ _animated: Bool)_
            ```
            - 뷰가 뷰 계층에서 사라지기 직전에 호출되는 메서드
            - 뷰가 생성된 뒤 발생한 변화를 이전상태로 되돌리기 좋은 시점
            - (= Android의 onPause() )
        * _func viewDidDisappear(_ _animated: Bool)_
            ```
            - 뷰가 뷰 계층에서 사라진 후 호출되는 메서드
            - 뷰를 숨기는 것과 관련된 추가적인 작업을 하기 좋은 시점
            - 시간이 오래 걸리는 작업은 하지 않는 것이 좋음
            - (= Android의 onStop() )
    * 레이아웃의 상태변화 메서드
        * _func viewWillLayoutSubviews()_
            ```
            - 뷰가 서브뷰의 레이아웃을 변경하기 직전에 호출되는 메서드
            - 서브뷰의 레이아웃을 변경하기 전에 수행할 작업을 하기 좋은 시점
        * _func viewDidLayoutSubviews()_
            ```
            - 서브뷰의 레이아웃이 변경된 후 호출되는 메서드
            - 서브뷰의 레이아웃을 변경 한 후 추가적인 작업을 수행하기 좋은 시점
    (ps. override 및 super 작성 필요)
- [x] __4. Delegation__
    ```
    * Delegate : (사전적의미) 위임하다, 선정하다, 대리하다
    * Delegation Design Pattern : 델리게이션 디자인 패턴은 하나의 객체가 다른 객체를 대신해 동작 또는 조정할 수 있는 기능을 제공
    * 델리게이트는 특정 상황에 대리자에게 메시지를 전달하고 그에 적절한 응답 받기 위한 목적으로 사용
    * control + command + click로 jump to definition 가능
    * 데이터소스(Data Source)
    * 프로토콜(Protocol)
    * (= Android의 implement methods)
- [x] __5. Singleton__
    * 디자인 패턴 중 하나
    * 특정 클래스의 인스턴스가 오직 하나임을 보장하는 객체 -> 다른 인스턴스들이 공유해서 사용할 수 있음.
    * 객체가 불필요하게 여러 개 만들어질 필요가 없는 경우에 많이 사용. 예를 들면 환경설정, 네트워크 연결처리, 데이터 관리 등
- [x] __6. Target-Action__
    * 디자인 패턴 중 하나
    * 객체는 이벤트가 발생할 때 다른 객체에 메시지를 보내는 데 필요한 정보를 포함.
    * 액션은 특정 이벤트가 발생했을 때 호출할 메서드를 의미(@IBAction). 타겟은 액션이 호출될 객체를 의미.(addTarget)
    * 이벤트 발생 시 전송된 메시지를 액션 메시지라고 하고, 타겟은 프레임워크 객체를 포함한 모든 객체가 될 수 있으나, 보통은 컨트롤러.
- [x] __7. Gesture Recognizer__
    * 특정 제스처 이벤트가 일어날 때 마다 각 타깃에 맞는 액션 메시지를 보내어 제스처 관련 이벤트를 처리가능
    * _UIGestureRecognizer의 하위클래스_
        ```
        - UITapGestureRecognizer : 싱글탭 또는 멀티탭 제스처
        - UIPinchGestureRecognizer : 핀치(Pinch) 제스처
        - UIRotationGestureRecognizer : 회전 제스처
        - UISwipeGestureRecognizer : 스와이프(swipe) 제스처
        - UIPanGestureRecognizer : 드래그(drag) 제스처
        - UIScreenEdgePanGestureRecognizer : 화면 가장자리 드래그 제스처
        - UILongPressGestureRecognizer : 롱프레스(long-press) 제스처
    * _UIGestureRecognizer의 주요 메서드_
        ```
        - init(target: Any?, action: Selector?) : 제스처 인식기를 타깃-액션의 연결을 통해 초기화
        - func location(in: UIView?) -> CGPoint : 제스처가 발생한 좌표를 반환
        - func addTarget(Any, action: Selector) : 제스처 인식기 객체에 타깃과 액션을 추가
        - func removeTarget(Any?, action: Selector?) : 제스처 인식기 객체로부터 타깃과 액션을 제거
        - func require(toFail: UIGestureRecognizer) : 여러 개의 제스처 인식기를 가지고 있을 때, 제스처 인식기 사이의 의존성을 설정
- [x] __8. Summary__
- - -
### 3. 기상정보 애플리케이션
- [x] __0.Hello!__
    * _새로 배우는 내용_
        ```
        * UIKit
            * UITableView
            * UITableViewCell
            * View Reuse
            * Table View Cell Customize
        * Swift
            * Codable
            * JsonDecoder
- [x] __1. 테이블뷰__
    * _테이블 뷰 스타일_
        ```
        * 일반 테이블뷰(Plain TableView)
            * 더 이상 나뉘지 않는 연속적인 행의 리스트 형태
            * 하나 이상의 섹션을 가질 수 있으며, 각 섹션은 여러 개의 행을 지닐 수 있음
            * 각 섹션은 헤더 혹은 푸터를 옵션으로 가질 수 있음
            * 색인을 이용한 빠른 탐색을 하거나 옵션을 선택할 때 용이
        * 그룹 테이블뷰(Grouped TableView)
            * 섹션을 기준으로 그룹화되어있는 리스트 형태
            * 하나 이상의 섹션을 가질 수 있으며, 각 섹션은 여러 개의 행을 지닐 수 있음
            * 각 섹션은 헤더 혹은 푸터를 옵션으로 가질 수 있음
            * 정보를 특정 기준에 따라 개념적으로 구분할 때 적합
            * 사용자가 정보를 빠르게 이해하는데 도움
    * _테이블 뷰 생성_
        ```
        * 동적 프로토타입(Dynamic Prototypes)
            * 셀 하나를 디자인해 이를 다른 셀의 템플릿으로 사용하는 방식
            * 같은 레이아웃의 셀을 여러 개 이용해 정보를 표시할 경우
            * 데이터 소스(UITableViewDataSource) 인스턴스에 의해 콘텐츠를 관리하며, 셀의 개수가 상황에 따라 변하는 경우에 사용
        * 정적 셀(Static Cells)
            * 고유의 레이아웃과 고정된 수의 행을 가지는 테이블뷰에 사용
            * 테이블뷰를 디자인하는 시점에 테이블의 형태와 셀의 개수가 정해져 있는 경우 사용
            * 셀의 개수가 변하지 않음
    * _테이블 뷰 구성요소_
        * 셀, 델리게이트, 데이터 소스
    * _데이터 소스_
        * 테이블뷰 데이터 소스 객체는 UITableViewDataSource 프로토콜을 채택
        * 데이터 소스는 테이블 뷰를 생성하고 수정하는데 필요한 정보를 테이블뷰 객체에 제공
        * 데이터 소스는 데이터 모델의 델리게이트로, 테이블뷰의 시각적 모양에 대한 최소한의 정보를 제공
        * UITableView 객체에 섹션의 수와 행의 수를 알려주며, 행의 삽입, 삭제 및 재정렬하는 기능을 선택적으로 구현가능
        * UITableViewDataSource 프로토콜의 주요 메서드는 아래와 같다.
        ```
        @required   :   필수적으로 구현되어야함
        - func tableView(UITableView, cellForRowAt: IndexPath) : 특정 위치에 표시할 셀을 요청하는 메서드
        - func tableView(UITableView, numberOfRowsInSection: Int) : 각 섹션에 표시할 행의 개수를 묻는 메서드
        @optional
        - func numberOfSections(in: UITableView) : 테이블뷰의 총 섹션 개수를 묻는 메서드
        - func tableView(UITableView, titleForHeaderInSection: Int) : 특정 섹션의 헤더 타이틀을 묻는 메서드
        - func tableView(UITableVIew, titleForFooterInSection: Int) : 특정 섹션의 푸터 타이틀을 묻는 메서드
        - func tableView(UITableVIew, commit: UITableViewCellEditingStyle, forRowAt: IndexPath) : 특정 위치의 행을 추가 또는 삭제 요청 메서드
        - func tableView(UITableView, canEditRowAt: IndexPath) : 특정 위치의 행이 편집 가능한 지 묻는 메서드
        - func tableView(UITableView, canMoveRowAt: IndexPath) : 특정 위치의 행을 재정렬 할 수 있는지 묻는 메서드
        - func tableVIew(UITableView, moveRowAt: IndexPath, to: IndexPath) : 특정 위치의 행을 다른 위치로 옮기는 메서드
    * _델리게이트_
        * 테이블뷰 델리게이트 객체는 UITableViewDelegate 프로토콜을 채택
        * 델리게이트는 테이블뷰의 시각적인 부분 수정, 행의 선택 관리, 액세서리뷰 지원 그리고 테이블뷰의 개별 행 편집을 도와줌
        * 델리게이트 메서드를 활용하면 테이블뷰의 세세한 부분을 조정할 수 있음
        * UITableViewDelegate 프로토콜의 주요 메서드는 아래와 같다.
        ```
        - func tableView(UITableView, heightForRowAt: IndexPath) : 특정 위치 행의 높이를 묻는 메서드
        - func tableView(UITableView, indentationLevelForRowAt: IndexPath) : 특정 위치 행의 들여쓰기 수준을 묻는 메서드
        - func tableView(UITableView, didSelectRowAt: IndexPath) : 지정된 행이 선택되었음을 알리는 메서드
        - func tableView(UITableVIew, didDeselectRowAt: IndexPath) : 지정된 행의 선택이 해제되었음을 알리는 메서드
        - func tableView(UITableView, viewForHeaderInSection: Int) : 특정 섹션의 헤더뷰를 요청하는 메서드
        - func tableView(UITableVIew, viewForFooterInSection: Int) : 특정 섹션의 푸터뷰를 요청하는 메서드
        - func tableView(UITableView, heightForHeaderInSection: Int) : 특정 섹션의 헤더뷰의 높이를 묻는 메서드
        - func tableView(UITableView, heightForFooterInSection: Int) : 특정 섹션의 푸터뷰의 높이를 묻는 메서드
        - func tableView(UITableView, willBeginEditingRowAt: IndexPath) : 테이블뷰가 편집모드에 들어갔음을 알리는 메서드
        - func tableView(UITableView, didEndEditingRowAt : IndexPath?) : 테이블뷰가 편집모드에서 빠져나왔음을 알리는 메서드
- [x] __2. 뷰의 재사용__
    * _재사용의 대표적인 예_
        ```
        - UITableViewCell: UITableView의 셀
        - UICollectionViewCell : UICollectionView의 셀
    * _재사용 원리_
        ```
        1. 테이블뷰 및 컬렉션뷰에서 셀을 표시하기 위해 데이터 소스에 뷰(셀) 인스턴스를 요청
        2. 데이터 소스는 요청마다 새로운 셀을 만드는 대신 재사용 큐에 재사용을 위해 대기하고 있는 셀이 있는지 확인, 있으면 그 셀에 새로운 데이터를 설정, 없으면 새로운 셀을 생성
        3. 테이블뷰 및 컬렉션뷰는 데이터 소스가 셀을 반환하면 화면에 표시
        4. 사용자가 스크롤을 하게 되면 일부 셀들이 화면 밖으로 사라지면서 다시 재사용 큐에 들어감
        5. 1~4번 과정이 반복
- [x] __3. 스토리보드 세그__
    * _세그란?_
        ```
        세그는 스토리보드에서 뷰 컨트롤러 사이의 화면전환을 위해 사용하는 객체이다. 별도의 코드 없이도 스토리보드에서 세그를 연결하여 뷰 컨트롤러 사이의 화면전환을 구현가능하다.
    * _UIStoryboardSegue 클래스_
        ```
        UIStoryboardSegue 클래스는 UIKit에서 사용할 수 있는 표준 화면전환을 위한 프로퍼티와 메서드를 포함한다. 세그는 뷰 컨트롤러의 뷰를 다른 뷰 컨트롤러의 뷰로 전환할 때 뷰 컨트롤러의 prepare(for:sender:) 메서드를 사용하여 새로 보여지는 뷰 컨트롤러에 데이터를 전달할 수 있다. (prepare는 주석으로 생성된다)
    * _주요 프로퍼티_
        ```
        var source: UIViewController : 세그에 전환을 요청하는 뷰 컨트롤러
        var destination: UIViewController : 전환될 뷰 컨트롤러
        var identifier: String? : 세그 객체의 식별자
    * _주요 메서드_
        ```
        func perform() : 뷰 컨트롤러의 전환을 수행
- [x]  __4. JSON 다루기__
    * _Codable_
        ```
        typealias Codable = Decodable & Encodable
    * _선언 예제_
        - Coordinate 타입과 Landmark 타입의 인스턴스를 다른 데이터형식으로 변환하고 싶은 경우
        ~~~
        struct Coordinate: Codable {
            var latitude: Double
            var longitude: Double
        }
    
        struct Landmark: Codable {
            var name: String
            var foundingYear: Int
            var vantagePoints: [Coordinate]
            var metadata: [String: String]
            var website: URL?
        }
       ~~~
       - CodingKey
            ```
            자주 사용하게 될 JSON형태의 데이터로 상호변환하고자 할 때는 기본적으로 JSON 타입의 키와 애플리케이션의 사용자 정의 프로퍼티가 일치해야한다. 만약 JSON의 키 이름을 구조체 프로퍼티의 이름과 다르게 표현하려면 타입 내부에 String 타입의 원시값을 갖는 CodingKeys라는 이름의 열거형을 선언하고 CodingKey 프로토콜을 준수하도록 하면 된다. CodingKeys 열거형 케이스의 이름은 해당 프로퍼티의 이름과 일치해야 한다. 그리고 프로퍼티의 열거형 케이스의 값으로 매칭할 JSON 타입의 키를 할당하면 된다. 만약, JSON 타입의 키와 프로퍼티 이름이 일치한다면 값을 할당하지 않아도 무방하다.
        ~~~
        struct Landmark: Codable {
            var name: String
            var foundingYear: Int
            var location: Coordinate
            var vantagePoints: [Coordinate]
            
            enum CodingKeys: String, CodingKey {
                case name = "title"
                case foundingYear = "founding_date"
                
                case location
                case vantagePoints
            }
        }
       ~~~
- [x]  __5. Summary__
