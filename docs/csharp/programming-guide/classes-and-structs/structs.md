---
title: 구조체 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 35b39da0b15c41b7b2c7a6567bea5dca3fb430e7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970312"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="a9c71-102">구조체(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a9c71-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="a9c71-103">구조체는 [struct](../../language-reference/keywords/struct.md) 키워드를 사용하여 정의합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
<span data-ttu-id="a9c71-104">구조체는 클래스와 대부분 동일한 구문을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="a9c71-105">구조체의 이름은 유효한 C# [식별자 이름](../inside-a-program/identifier-names.md)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="a9c71-106">구조체는 다음과 같은 방법으로 클래스보다 더 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="a9c71-107">구조체 선언 내에서 필드가 const 또는 static으로 선언된 경우가 아니면 필드를 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="a9c71-108">구조체는 매개 변수 없는 생성자(매개 변수가 없는 생성자) 또는 종료자를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-108">A struct cannot declare a parameterless constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="a9c71-109">할당 시 구조체가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-109">Structs are copied on assignment.</span></span> <span data-ttu-id="a9c71-110">구조체를 새 변수에 할당하면 모든 데이터가 복사되고, 새 복사본을 수정해도 원래 복사본의 데이터는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="a9c71-111">`Dictionary<string, myStruct>`와 같은 값 형식의 컬렉션으로 작업할 때 이 점을 명심해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="a9c71-112">구조체는 참조 형식인 클래스와 달리 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="a9c71-113">클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="a9c71-114">구조체는 매개 변수가 있는 생성자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-114">Structs can declare constructors that have parameters.</span></span>
- <span data-ttu-id="a9c71-115">구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="a9c71-116">모든 구조체는 <xref:System.Object>에서 상속하는 <xref:System.ValueType>에서 직접 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="a9c71-117">구조체는 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-117">A struct can implement interfaces.</span></span>
- <span data-ttu-id="a9c71-118">변수가 nullable 값 형식으로 선언되지 않으면 구조체는 `null`일 수 없으며 구조체 변수에 `null`을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c71-118">A struct cannot be `null`, and a struct variable cannot be assigned `null` unless the variable is declared as a nullable value type.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a9c71-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9c71-119">See also</span></span>

- [<span data-ttu-id="a9c71-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a9c71-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a9c71-121">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="a9c71-121">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="a9c71-122">클래스</span><span class="sxs-lookup"><span data-stu-id="a9c71-122">Classes</span></span>](classes.md)
- [<span data-ttu-id="a9c71-123">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="a9c71-123">Nullable value types</span></span>](../../language-reference/builtin-types/nullable-value-types.md)
- [<span data-ttu-id="a9c71-124">식별자 이름</span><span class="sxs-lookup"><span data-stu-id="a9c71-124">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="a9c71-125">구조체 사용</span><span class="sxs-lookup"><span data-stu-id="a9c71-125">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="a9c71-126">메서드에 대한 구조체 전달과 클래스 참조 전달 간의 차이점을 이해하는 방법</span><span class="sxs-lookup"><span data-stu-id="a9c71-126">How to know the difference between passing a struct and passing a class reference to a method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
