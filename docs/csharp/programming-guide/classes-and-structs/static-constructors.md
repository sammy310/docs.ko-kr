---
title: 정적 생성자 - C# 프로그래밍 가이드
description: C#의 정적 생성자는 정적 데이터를 초기화하거나 첫 번째 인스턴스가 작성되거나 정적 멤버가 참조되기 전에 한 번만 수행되는 작업을 수행합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: e324b2aa968ff5fdf9c268fa3891f67e8530ff87
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86863984"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="f1188-103">정적 생성자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f1188-103">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="f1188-104">정적 생성자는 [정적](../../language-reference/keywords/static.md) 데이터를 초기화하거나 한 번만 수행해야 하는 특정 작업을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-104">A static constructor is used to initialize any [static](../../language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="f1188-105">첫 번째 인스턴스가 만들어지거나 정적 멤버가 참조되기 전에 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-105">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  

## <a name="remarks"></a><span data-ttu-id="f1188-106">설명</span><span class="sxs-lookup"><span data-stu-id="f1188-106">Remarks</span></span>
<span data-ttu-id="f1188-107">정적 생성자에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-107">Static constructors have the following properties:</span></span>  
  
- <span data-ttu-id="f1188-108">정적 생성자는 액세스 한정자를 사용하거나 매개 변수를 갖지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-108">A static constructor does not take access modifiers or have parameters.</span></span>  

- <span data-ttu-id="f1188-109">클래스 또는 구조체에는 한 개의 정적 생성자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-109">A class or struct can only have one static constructor.</span></span>

- <span data-ttu-id="f1188-110">정적 생성자는 상속하거나 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-110">Static constructors cannot be inherited or overloaded.</span></span>

- <span data-ttu-id="f1188-111">정적 생성자는 직접 호출할 수 없으며, CLR(공용 언어 런타임)을 통해서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-111">A static constructor cannot be called directly and is only meant to be called by the common language runtime (CLR).</span></span> <span data-ttu-id="f1188-112">자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-112">It is invoked automatically.</span></span>

- <span data-ttu-id="f1188-113">사용자는 프로그램에서 정적 생성자가 실행되는 시기를 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-113">The user has no control on when the static constructor is executed in the program.</span></span>
  
- <span data-ttu-id="f1188-114">정적 생성자는 첫 번째 인스턴스가 만들어지거나 정적 멤버가 참조되기 전에 자동으로 호출되어 [클래스](../../language-reference/keywords/class.md)를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-114">A static constructor is called automatically to initialize the [class](../../language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span> <span data-ttu-id="f1188-115">정적 생성자는 인스턴스 생성자보다 먼저 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-115">A static constructor will run before an instance constructor.</span></span> <span data-ttu-id="f1188-116">유형의 정적 생성자는 이벤트 또는 대리자에 할당된 정적 메서드가 호출될 때 호출되며 할당될 때는 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-116">A type's static constructor is called when a static method assigned to an event or a delegate is invoked and not when it is assigned.</span></span> <span data-ttu-id="f1188-117">정적 필드 변수 이니셜라이저가 정적 생성자의 클래스에 있는 경우 정적 생성자가 실행되기 직전에, 클래스 선언에 나타나는 텍스트 순서대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-117">If static field variable initializers are present in the class of the static constructor, they will be executed in the textual order in which they appear in the class declaration immediately prior to the execution of the static constructor.</span></span>

- <span data-ttu-id="f1188-118">정적 필드를 초기화하는 정적 생성자를 제공하지 않으면 모든 정적 필드가 [C# 형식의 기본값](../../language-reference/builtin-types/default-values.md)에 나열된 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-118">If you don't provide a static constructor to initialize static fields, all static fields are initialized to their default value as listed in [Default values of C# types](../../language-reference/builtin-types/default-values.md).</span></span>
  
- <span data-ttu-id="f1188-119">정적 생성자가 예외를 throw하는 경우 런타임에서 생성자를 다시 호출하지 않으며, 프로그램을 실행 중인 애플리케이션 도메인의 수명 동안 형식이 초기화되지 않은 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-119">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span> <span data-ttu-id="f1188-120">가장 일반적으로, 정적 생성자가 형식을 인스턴스화할 수 없는 경우 또는 정적 생성자 내에서 발생하는 처리되지 않은 예외에 대해 <xref:System.TypeInitializationException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-120">Most commonly, a <xref:System.TypeInitializationException> exception is thrown when a static constructor is unable to instantiate a type or for an unhandled exception occurring within a static constructor.</span></span> <span data-ttu-id="f1188-121">소스 코드에서 명시적으로 정의되지 않은 암시적 정적 생성자의 경우 문제 해결을 위해 IL(중간 언어) 코드를 검사해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-121">For implicit static constructors that are not explicitly defined in source code, troubleshooting may require inspection of the intermediate language (IL) code.</span></span>

- <span data-ttu-id="f1188-122">정적 생성자가 있으면 <xref:System.Reflection.TypeAttributes.BeforeFieldInit> 형식 특성을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-122">The presence of a static constructor prevents the addition of the <xref:System.Reflection.TypeAttributes.BeforeFieldInit> type attribute.</span></span> <span data-ttu-id="f1188-123">이 때문에 런타임 최적화가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-123">This limits runtime optimization.</span></span>

- <span data-ttu-id="f1188-124">`static readonly`로 선언된 필드는 해당 선언의 일부로 또는 정적 생성자에서만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-124">A field declared as `static readonly` may only be assigned as part of its declaration or in a static constructor.</span></span> <span data-ttu-id="f1188-125">명시적 정적 생성자가 필요하지 않은 경우, 런타임 최적화 향상을 위해 정적 생성자를 통하지 않고 선언에서 정적 필드를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-125">When an explicit static constructor is not required, initialize static fields at declaration, rather than through a static constructor for better runtime optimization.</span></span>

> [!Note]
> <span data-ttu-id="f1188-126">직접 액세스할 수 없더라도, 명시적 정적 생성자가 있을 경우 초기화 예외 문제 해결에 도움이 되도록 문서화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-126">Though not directly accessible, the presence of an explicit static constructor should be documented to assist with troubleshooting initialization exceptions.</span></span>

### <a name="usage"></a><span data-ttu-id="f1188-127">사용법</span><span class="sxs-lookup"><span data-stu-id="f1188-127">Usage</span></span>

- <span data-ttu-id="f1188-128">정적 생성자는 일반적으로 클래스가 로그 파일을 사용하고, 생성자를 사용하여 이 파일에 항목을 쓰는 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-128">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
- <span data-ttu-id="f1188-129">정적 생성자는 생성자가 `LoadLibrary` 메서드를 호출할 수 있을 때 비관리 코드에 대한 래퍼 클래스를 만드는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-129">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  

- <span data-ttu-id="f1188-130">또한 정적 생성자를 사용하면 제약 조건(형식 매개 변수 제약 조건)을 통해 컴파일 시간에 검사할 수 없는 형식 매개 변수에 런타임 검사를 편리하게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-130">Static constructors are also a convenient place to enforce run-time checks on the type parameter that cannot be checked at compile time via constraints (Type parameter constraints).</span></span>

## <a name="example"></a><span data-ttu-id="f1188-131">예제</span><span class="sxs-lookup"><span data-stu-id="f1188-131">Example</span></span>
 <span data-ttu-id="f1188-132">이 예제에서 `Bus` 클래스에는 정적 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-132">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="f1188-133">`Bus`의 첫 번째 인스턴스를 만들 때(`bus1`) 정적 생성자가 호출되어 클래스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-133">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="f1188-134">샘플 출력은 `Bus`의 두 인스턴스가 생성된 경우에도 정적 생성자가 한 번만 실행되고, 인스턴스 생성자를 실행하기 전에 실행되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-134">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="f1188-135">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f1188-135">C# language specification</span></span>
<span data-ttu-id="f1188-136">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [정적 생성자](~/_csharplang/spec/classes.md#static-constructors) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1188-136">For more information, see the [Static constructors](~/_csharplang/spec/classes.md#static-constructors) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f1188-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1188-137">See also</span></span>

- [<span data-ttu-id="f1188-138">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f1188-138">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f1188-139">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="f1188-139">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="f1188-140">생성자</span><span class="sxs-lookup"><span data-stu-id="f1188-140">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="f1188-141">정적 클래스 및 정적 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="f1188-141">Static Classes and Static Class Members</span></span>](./static-classes-and-static-class-members.md)
- [<span data-ttu-id="f1188-142">종료자</span><span class="sxs-lookup"><span data-stu-id="f1188-142">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="f1188-143">생성자 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="f1188-143">Constructor Design Guidelines</span></span>](../../../standard/design-guidelines/constructor.md#type-constructor-guidelines)
- [<span data-ttu-id="f1188-144">보안 경고 - CA2121: 정적 생성자는 private이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1188-144">Security Warning - CA2121: Static constructors should be private</span></span>](https://docs.microsoft.com/visualstudio/code-quality/ca2121-static-constructors-should-be-private)
