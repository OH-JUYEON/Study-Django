##STUDY
<a name="readme-top"></a>
## Django 

#### Framework

	뼈대나 근간을 이루는 코드들의 묶음.
	라이브러리나, 개발자가 작성해놓은 코드파일을 의미하며
	API란, 여러 라이브러리가 모여있는 패키지(JAR)를 의미한다.
	프레임워크란, API가 굉장히 많이 모여저서 덩치가 커져있는 것을 의미한다.
	개발자는 각 개개인의 능력차이가 큰 직종이고, 개발자 구성에 따라 프로젝트 결과 역시
	큰 차이를 낳는다. 이런 상황을 극복하기 위한 코드의 결과물이 바로 프레임워크이다.
	프로그램의 기본 흐름이나 구조를 정하고 모든 팀원이 이 구조에 자신의 코드를 추가하는 방식으로
	개발하게 된다.

  
#### Framework의 장점

	개발에 필요한 구조를 이미 코드로 만들어 놓았기 때문에, 실력이 부족한 개발자라 하더라도
	반쯤 완성된 상태에서 필요한 부분을 조립하는 형태의 개발이 가능하다.
	회사 입장에서는 프레임워크를 사용하면 일정한 품질이 보장되는 결과물을 얻을 수 있고,
	개발자 입장에서는 완성된 구조에 자신이 맡은 서비스에 대한 코드를 개발해서 넣기 때문에
	개발 시간을 단축할 수 있다.


#### Django Framework

	파이썬으로 만들어진 무료 오픈 소스 웹 애플리케이션 프레임워크이며,
	빠르고 쉽게 웹사이트를 개발할 수 있는 구성요소로 이루어진 웹 프레임워크이다.


#### Django Framework의 장점

	- 프로젝트 전체 구조를 설계할 때 유용하다(빠른 속도로  서버 제작 가능)
	- 다른 프레임워크들의 포용, 여러 프레임워크를 혼용해서 사용 가능하며 이를 접착성이 좋다고 한다.
	- 개발 생산성과 개발도구의 지원
 	- 확장성 : 객체를 기억하여 재사용할 수 있는 캐싱과 코드 재사용 기능으로 인해 확장성이 좋다.
 	- 보안 : 개발자가 SQL 주입, CSRF 공격 및 XSS와 같은 많은 보안 문제를 피할 수 있도록 도와준다.
 	- 기본 라이브러리를 통한 빠른 개발 : 처음부터 코드를 작성하는 대신 여러 기능을 포함하는 패키지를 활용할 수 있다.
 

#### Django Framework의 특징

	1. MVT 패턴
		Model: 테이블에 저장되거나 불러온 데이터
		View: 테이블에 접근하고 Template에 데이터를 전달
		Templates: 클라이언트에게 보여질 화면 구성

	2. 강력한 ORM
		ORM(Object Relational Mapping)은 객체 관계 매핑이며,
		객체 진영과 RDB진영의 구조 차이를 자동으로 해결해주는 기술의 총칭이다.
		오로지 객체를 중심으로 설계가 가능하며, 직접 SQL문을 작성하지 않아도
		자동으로 쿼리가 생성되어 실행된다.	

	3. 자체적인 템플릿
		HTML에서 연산이 가능하도록 도와주며, 자체 템플릿 태그가 있기 때문에
		동적인 페이지를 구성할 수 있게 해준다.

	4. 소스코드 변경 감지
		.py파일의 소스코드가 변경된다면, 이를 자동으로 감지하여 서버를 재시작해준다.

	5. 단위 테스트
		서버를 실행하지 않아도 기능별 단위 테스트가 가능하기 때문에
		버그를 줄이고 개발 시간을 단축할 수 있다.



#### ▶ Django Framework의 목적

	간단한 웹 앱을 제작하거나 Python을 필요로 하는 서비스들을 가볍게 제작하여, MSA로 나누어 개발하는
	목적으로 사용한다. 대규모 프로젝트를 Django Framework 하나로 개발하기에는 적합하지 않다.


#### ▶ Django 기본 명령어

	애플리케이션 생성
		python manage.py startapp [애플리케이션명]

	마이그레이션 파일 생성	
		python manage.py makemigrations

	마이그레이션 진행
		python manage.py migrate

	마이그레이션 삭제
		python manage.py migrate --fake [앱이름] zero

	서버 실행
		python manage.py runserver [포트번호]

	admin 페이지 회원가입
		python manage.py createsuperuser


#### ▶ Django import

	압축 파일 해제 후 venv 폴더 삭제
	파이참에서 open으로 열기
	File -> Settings -> Project:000 
	-> Add Interpreter -> +버튼 -> Add Local Interpreter 
	-> 좌측 Virtual ... 선택 -> Add 클릭
	requirements.txt 파일에서 다시 라이브러리 install



#### ▶ Model

	Django에서 모델이라는 추상화된 클래스를 사용하여 데이터베이스에 테이블을 정의할 수 있다.
	models.Model을 상속받은 클래스로 구현할 수 있으며, 내부 클래스로 Meta 클래스를 선언할 수 있다.


#### ▶ Model Convention

	모델 내 코드를 작성할 때 아래의 순서에 맞춰 작성하는 것을 권장한다.

	1. Constant for choices
	2. All databases Fields
	3. Custom manager attributes
	4. class Meta
	5. def __str__()
	6. def save()
	7. def get_absolute_url()
	8. Any custom methods



#### 1.Constant for choices

	DB에 저장할 값과 실제 화면에 보여지는 값이 다를 경우 미리 튜플 형태로 선언해 놓고 사용한다.

	CONSTANT = [
		('DB 저장 값', '보여질 값'),
		...
	]


#### 2. All databases Fields

	default는 제약조건을 추가해주지 않고, 파이썬에서 값을 넣어주는 역할을 한다.
	
	ForeignKey(to, verbose_name, related_name, related_query_name, on_delete, null)
	OneToOneField(to, verbose_name, related_name, related_query_name, on_delete, null)
	ManyToManyField(to, verbose_name, related_name, related_query_name, through)

		related_name
			역참조가 필요한 다대다 또는 일대다 관계에서 유용하게 사용된다.
			B필드에 A객체를 참조 시 b.a로 접근할 수 있으나 역참조인 a.b로는 접근할 수 없다.
			A필드에는 B필드가 없기 때문이다. 이 때에는 Django에서 자동으로 만들어지는
			_set객체를 사용하여 역참조가 가능하다. 즉, a.b_set으로 역참조가 가능하다.
			만약 _set객체의 이름을 다른 이름으로 사용하고자 할 때 바로 related_name을 사용한다.

		related_query_name
			DML 메소드 사용 시 속성명으로 사용될 이름. 즉, 쿼리에 사용될 이름을 작성한다.

		on_delete
			삭제 시 CASCADE, SET_NULL


	CharField(verbose_name, max_length, choices, unique, blank, null, default)
		최대 길이 제한이 필요한 경우
	TextField(verbose_name, null=False, blank=True)
		최대 길이 제한이 필요 없을 경우

		문자열 필드는 null=False로 하고 필수 요소가 아니라면 blank=True로 설정한다.
		이렇게 설정하는 이유는 null과 빈 값을 "null이거나 빈 문자열일 경우 빈 값이다"라고 검사할 필요 없이
		"빈 문자열인지"로만 판단할 수 있게 되기 때문이다.

	PositiveSmallIntegerField(verbose_name, choices, null, default)
	SmallIntegerField(verbose_name, choices, null, default)
	IntegerField(verbose_name, choices, null, default) : 4byte

		정수 필드는 max_length를 직접 지정하지 않고 기본적으로 byte가 정해져있다.

	BooleanField(verbose_name, default)

	DateField(verbose_name, null, default)
	TimeField(verbose_name, null, default)
	DateTimeField(verbose_name, null, default)

		auto_now=True 설정하면 해당 객체가 변경될 때마다
		자동으로 필드 값을 현재 시간으로 수정한다. 마지막 수정 날짜 항목으로 사용된다.
		auto_now_add=True 설정하면 최초 한 번만
		자동으로 필드 값을 현재 시간으로 수정한다. 처음 등록된 날짜 항목으로 사용된다.

#### 3. Custom manager attributes

	데이터베이스와 상호작용하는 인터페이스이며, Model.objects 속성을 통해 사용한다.
	Custom Manager와 Custom QuerySet을 통해 사용할 수 있으며,
	공통적으로 사용되는 쿼리를 공통 함수로 정의할 수 있고 실제 동작을 숨길 수 있다.


#### 4. class Meta

	Model 클래스 안에 선언되는 내부 클래스이며, 모델에 대한 기본 설정들을 변경할 수 있다.
	Meta 클래스가 작동하기 위해서는 정해진 속성과 속성 값을 작성해야 하고
	이를 통해 Django를 훨씬 편하게 사용할 수 있다.

	ordering = ['필드명']	# 오름차순
	ordering = ['-필드명']	# 내림차순

	db_table = '테이블명'	# 테이블명 작성

	abstract = True		# Table로 생성하지 않음, 객체 진영에서의 상속관계 시 부모 클래스에 설정
				  자식 클래스의 Meta는 abstract = False로 자동 설정


#### 5. def __str__()

	객체 조회 시 원하는 데이터를 직접 눈으로 확인하고자 할 때 사용하며,
	객체 출력 시 자동으로 사용되는 메소드이다.
	모델 필드 내에서 재정의하여 원하는 필드를 문자열로 리턴하면 앞으로 객체 출력 시 해당 값이 출력된다.

#### 6. def save()

	모델 클래스를 객체화한 뒤 save()를 사용하면 INSERT 쿼리가 발생한다.
	이는 Django에서 자동으로 지원해주는 메소드이지만, save() 사용 시
	INSERT 쿼리 발생 외 다른 로직이 필요할 경우 재정의할 수 있다.
	또한 RDB에 이미 있는 객체로 save()를 사용하게 되면 필드 데이터 변경을 감지하여
	변경된 데이터가 있을 경우 UPDATE 쿼리가 발생한다.
	하지만 재정의를 하면, 객체를 대량으로 생성하거나 업데이트할 때 동작하지 않는다.

 #### 7. def get_absolute_url()

	모델에 대해서 상세보기(DetailView)를 제작한다면, redirect(모델 객체)를 통해
	자동으로 get_absolute_url()을 호출한다.
	추가 혹은 수정 서비스 후 상세보기 페이지로 이동하게 된다면
	매번 redirect에 경로를 작성하지 않고 get_absolute_url()를 재정의하여 사용하는 것을 추천한다.


#### 생성(CREATE)
	1. create()와 save()
	2. bulk_create()
	3. get_or_create()

 
	1. create()와 save()
		모델명.objects.create()는 전달한 값으로 초기화 된 새로운 객체를 생성하고 테이블에 저장한다. 
		하지만 객체명.save()는 이미 객체를 생성한 뒤 사용하기 때문에 객체를 리턴하지 않는다.

		일반적으로 기존 객체에 자주 영향을 미치는 메소드는 자신을 리턴하지 않도록 하는 것이
		Python에서 좋은 사례로 간주된다.
		예를 들어 sorted(list)는 정렬된 목록을 리턴하지만 list.sort()는 원본을 정렬한 뒤
		아무 것도 리턴하지 않는다.
		만약 객체로 접근한 메소드가 자신을 리턴하게 되면 계속 이어서 코드를 작성하게 되고(메소드 체인),
		이 때 특정 버그나 문제가 중간에 발생하게 되면 찾기가 힘들 뿐더러 전체 기능에 문제가 생길 수 있다.

	2. bulk_create()
		모델명.objects.bulk_create([])는 전달한 list로 초기화 된 여러 개의 객체를 생성하고 테이블에 저장한다.
		생성된 객체들은 list 타입으로 리턴된다.

	3. get_or_create()
		모델명.objects.get_or_create()는 테이블에 객체가 있으면 가져오고, 없으면 새롭게 생성하고 저장한다.
		두 칸짜리 tuple 타입으로 리턴되며, 첫 번째는 객체, 두 번째 생성여부인 bool 타입이 담겨있다.


#### 조회(READ)

	1. get()
	2. all()
	3. values()
	4. values_list()
	5. filter()
	6. exists()
	7. exclude()
	8. AND, OR
	9. first(), last()
	10. count()
	11. order_by()
	12. annotate()
	13. aggregate()


	1. get()
		테이블에서 조건에 맞는 한 개의 객체를 조회한다.
		조회된 값이 없으면 DoseNotExist, 2개 이상이면 MultipleObjectsReturned가 발생하기 때문에
		조회할 값이 1개일 때만 사용한다.

	2. all()
		테이블에서 전체 정보를 조회한다.
		QuerySet 객체를 리턴하며, 조회된 객체들이 들어있다.
		QuerySet이란, 쿼리의 결과를 전달받은 모델 객체 목록이다. 리스트와 구조는 같지만,
		파이썬 기본 자료구조가 아니기 때문에 형변환이나 serializers가 필요하다.

	3. values()
		테이블에서 전체 정보를 조회한다.
		QuerySet 객체를 리턴하며, 조회된 객체가 dict 타입으로 들어있다.
		필드 이름을 전달하면 원하는 필드 정보만 가져올 수 있다.

	4. values_list()
		테이블에서 전체 정보를 리턴한다.
		QuerySet 객체를 리턴하면, 조회된 객체가 tuple 타입으로 들어있다.
		KEY가 없기 때문에 value만 존재하며, 인덱스로만 접근 가능하다.

	5. filter()
		조건에 맞는 행을 조회한다.
		QuerySet 객체를 리턴하며, 조회된 객체들이 들어있다.
		조건에 맞는 결과가 한 개도 없을 경우 빈 QuerySet이 리턴된다.

	6. exists()
		filter()와 함께 사용해서 filter 조건에 맞는 데이터가 있는지 조회한다.

	7. exclude()
		조건에 맞지 않는 행을 조회한다.
		QuerySet 객체를 리턴하며, 조회된 객체들이 들어있다.
		조건에 맞는 결과가 한 개도 없을 경우 빈 QuerySet이 리턴된다.

	8. AND, OR
		모델명.objects.filter() & 모델명.objects.filter()
		모델명.objects.filter() | 모델명.objects.filter()

		모델명.objects.filter(key=value, key=value)
		모델명.objects.filter(Q(key=value) | Q(key=value))

	9. first(), last()
		모델명.objects.first()는 조건에 맞는 QuerySet 결과 중 첫 번째 객체를 리턴하고
		모델명.objects.last()는 조건에 맞는 QuerySet 결과 중 마지막 객체를 리턴한다.

	10. count()
		모델명.objects.filter().count()로 사용하며 조건에 맞는 결과 개수를 리턴한다.

	11. order_by()
		특정 필드를 기준으로 정렬을 진행한다.

		모델명.objects.order_by('필드명')은 오름차순이며,
		모델명.objects.order_by('-필드명')은 내림차순이다.

	12. annotate()
		결과 테이블에서 컬럼을 다른 이름으로 사용하거나 다른 연산을 수행한 뒤 새로운 이름을 만들어낸다.

	13. aggregate()
		QuerySet객체.aggregate(key=집계함수('필드명')는 전체를 대상으로 하고
		QuerySet객체.values("묶을 필드명").annotate(key=집계함수('필드명'))는 그룹을 대상으로 한다.



#### 수정(UPDATE)

	1. update()
	2. save()

 
	1. update()
		존재하는 객체의 필드를 수정하고 수정된 행의 수를 리턴한다.
		객체.update(key=value)


	2. save()
		존재하는 객체를 조회한 뒤 직접 필드를 수정하고 save()를 사용하면 수정된다.
		객체.save()



#### 삭제(DELETE)
	delete()
		객체.delete()로 사용하며 조건에 맞는 모든 행을 삭제한다.
		get(), filter(), all()과 같이 사용된다.

#### ▶ Bean등록

@Bean
	Bean은 스프링 프레임워크에서 관리되는 객체를 의미
	@Bean Annotation은 개발자가 제어가 불가능한 외부 라이브러리와 같은 것들을 Bean으로 만들 때 사용
	스프링 컨테이너에 Bean으로 등록하기 위해
	예) @Component, @Service, @Repository, @Controller


#### ▶ 의존성 주입(Dependency Injection)

	객체 간의 관계를 자동으로 설정하기 위해
	@Autowired


#### ▶ 트랜잭션 관리

트랜잭션 
	데이터베이스의 상태를 변경하는 일련의 작업을 하나의 논리적인 단위로 묶은 것.
	이 작업들은 모두 성공적으로 수행되어야 하며, 그렇지 않을 경우 이전 상태로 롤백
	@Transactional


#### ▶ MVC 웹 애플리케이션 개발

	스프링 MVC를 사용하여 웹 애플리케이션을 개발할 때 어노테이션을 활용
	@Controller, @RequestMapping, @RequestParam, @ResponseBody 등의 어노테이션을 사용하여 요청을 처리하고 응답을 생성


#### @Controller

@Controller
	Controller의 역할을 수행 한다고 명시(해당 클래스를 Controller로 사용한다고 Spring FrameWork에 알린다.)

   	필요한 비즈니스 로직을 호출하여 전달할 모델(Model)과 이동할 뷰(View) 정보를 DispatherServlet에 반환 한다.

 	- Bean으로 등록

 	- @Component의 구체화 된 어노테이션
	frontController처럼 쓸 수 있다.

<img width="900" src="https://github.com/coder-juyeon/Spring/assets/122768623/efc551ae-b8a1-42c4-973d-2f2641e0103c">


#### @RequestMapping

	class와 Method를 같이 쓸때
	예) @RequestMapping("/ex/")
	공통적인 url을 설정해줌


#### @ModelAttribute

	@ModelAttribute("name")String name
	html에서 jstl을 쓰기 위해
	매개변수에 주기
	예)
	@GetMapping("ex04")
	    public void ex04(String name, Model model) {
		model.addAttribute("name", name);
		log.info(name);
	}

	= (위와 아래가 같음)

	@GetMapping("ex04")
	    public void ex04(@ModelAttribute("name")String name) {
		log.info(name);
	}


#### @RequestParam

@RequestParam
	1대1 매핑
	화면에서 받을 파라미터 이름과 자바에서 받을 매개변수 이름이 다를때 사용한다.
	예) 파라미터는 address(화면) 매개변수는 city면
	    @RequestParam("address") String city
    
@RequestParam, @ModelAttribute의 차이점
	modelAttribute은 파라미터를 객체 타입으로 받을 수 있지만
	RequestParam은 1대1 매핑으로 파라미터에 데이터 하나만 가져올 수 있다.

	예)
	public class UserSearchForm() {
		private int id;
		private String name;
		private String email;
		private String phone;
	}

	@ModelAttribute의 경우
	public String getTestPage(@ModelAttribute UserSearchForm userSearchForm){
	}

	@RequestParam의 경우
	public String getTestPage(@RequestParam int id, @RequestParam String name, @RequestParam String email,@RequestParam String phone){
	}


#### Assertions.asertThat()

 	친절한 오류 설명 및 빠른 단위 테스트 가능
 	assertj꺼 쓰기


#### REST

	- Representational State Transfer
	- 자원, 행위, 표현으로 구성되어 있다.
	- 언제, 어디서든 누구든 서버에 요청을 보낼 때 URI만으로도 데이터 및 CRUD의 상태를 이해할 수 있도록 설계하는 규칙.
	- HTTP에 존재하는 모든 자원에 고유한 URI를 부여하여 활용하는 것으로 자원을 정의하고 자원에 대한 주소를 지정하는 방법론
	- JSON 혹은 XML을 통해 데이터를 주고 받는 것이 일반적 
	- 네트워크 상에서 Client와 Server사이의 통신 방식 중 하나
	- HTTP URL을 통해 자원을 명시하고 HTTP Method(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미

	* CRUD Operation
	Create : 생성(POST)
	Read : 조회(GET)
	Update : 수정(PUT)
	Delete : 삭제(DELETE)

	* RESTful
	-REST 방식을 따른 시스템

	* RESTful API
	-설계 방식이 모두 REST 규칙에 의해 작성된 API.


#### 3-tier

	3-tier
	   스프링 프로젝트는 3-tier 방식으로 구성한다.

	   ▶ Presentation Tier - 화면 계층
	      화면에 보여주는 기술을 사용하는 영역

	   ▶ Buisiness Tier - 비지니스 계층, 로직 계층
	      순수한 비지니스 로직을 담고 있는 영역

	   ▶ Persistence Tier - 영속 계층, 데이터 계층
	      데이터를 어떤 방식으로 보관하고, 사용하는 가에 대한 설계가 들어가는 영역

	3-tier의 목적
		각 영역은 독립적으로 설계되어 
		나중에 특정 기술이 변하더라도 필요한 부분을 전자제품의 부품처럼 쉽게 교환할 수 있게 하자는 방식이다.

	3-tier의 구조
		Presentation ↔ Business ↔ Persistence ↔ DBMS
				↑      ↑         ↑
			Controller   Service       Mapper

#### REST URI 규칙

	1. 소문자로 작성한다.
		대문자로 작성시 문제가 발생할 수 있기 때문에 소문자로 작성한다.

	2. 언더바 대신 하이픈을 사용한다.
		가독성을 높이기 위해서 하이픈으로 구분하는 것이 좋다.

	3. URI 마지막은 슬래시를 작성하지 않는다.	
		마지막에 작성하는 슬래시는 의미가 없다.		

	4. 계층 관계 표현 시 슬래시 구분자로 사용한다.
		계층 관계(포함 관계)에서는 슬래시로 구분해준다.

	5. 동사는 작성하면 안된다.
		행위는 URI로 표현하지 않고 HTTP METHOD를 통해 전달한다.
	
	6. 파일 확장자는 포함시키지 않는다.
		파일 확장자는 URI로 표현하지 않고 Header의 Content-Type을 사용하여
		body의 내용을 처리하도록 설계한다.

	7. 데이터를 대표할 때에는 명사를 사용하지만, 상태를 대표할 때에는 동사를 허용한다.
		http://www.app.com/writing (X)
		http://www.app.com/write (O)		

	8. URI에 사용되는 영어단어는 복수로 작성한다.



#### AOP(Aspect Oriented Programming)

	기존 코드와 부가 기능 코드를 따로 정의한 뒤 다시 합쳐서 모듈로 만드는 것이다.
	코드의 중복을 줄일 수 있으며, 핵심 로직과 주변 로직을 분리하여 관리할 수 있다.
	핵심 로직은 아니지만 반복적으로 개발에 필요한 관심사들을 주변 로직이라고 한다.
	따라서 AOP는 이러한 주변 로직을 횡단 관심사로 분리하여 작성하고 종단 관심사인
	핵심 비지니스 로직만을 해당 서버에서 작성하도록 한다.

	예) 나눗셈 프로그램 개발 시 두 개의 숫자를 나누는 것(핵심, 종단)
	0으로 나누는 지 검사하는 것(주변, 횡단)

	즉, 반복적으로 나타나는 횡단 관심사를 모듈로 분리한 후 적절한 시점에 로직을 주입하는 것이 AOP이다.
	스프링에서는 별도의 복잡한 설명 없이 간편하게 AOP의 기능들을 구현할 수 있기 때문에 중요한 특징 중 하나이다.

#### AOP를 사용할 수 있는 시점

	- Around(전 구역)
	- Before(메소드 시작 직후)
	- After(메소드 종료 직전)
	- AfterReturning(메소드 리턴 후)
	- AfterThrowing(메소드 예외 발생 후)


#### AOP 설계 순서

	1. 구현할 횡단 관심사를 의미할 수 있는 어노테이션 만들기
	2. 어노테이션을 Aspect로 등록하기
	3. 종단 관심사에 등록된 어노테이션 사용하기


<img width="900" src ="https://github.com/coder-juyeon/Spring/assets/122768623/2cea959c-d094-4328-aa52-97b58ce4e58b">

<p align="right">(<a href="#readme-top">back to top</a>)</p>
