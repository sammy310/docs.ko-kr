---
title: 쿼리에서 요소 속성의 하위 집합을 반환하는 방법 - C# 프로그래밍 가이드
description: C#에서 쿼리 표현식의 익명 형식을 사용하여 각 원본 요소의 속성 중 일부를 반환하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 3e30793ed16204943e2398984ed200b93db7f86f
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95098856"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="3a34e-103">쿼리에서 요소 속성의 하위 집합을 반환하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="3a34e-103">How to return subsets of element properties in a query (C# Programming Guide)</span></span>

<span data-ttu-id="3a34e-104">이러한 조건이 둘 다 적용되는 경우 쿼리 식에서 무명 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34e-104">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
- <span data-ttu-id="3a34e-105">각 소스 요소의 속성 중 일부만 반환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34e-105">You want to return only some of the properties of each source element.</span></span>  
  
- <span data-ttu-id="3a34e-106">쿼리가 실행되는 메서드의 범위 외부에 쿼리 결과를 저장할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a34e-106">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="3a34e-107">각 소스 요소에서 하나의 속성 또는 필드만 반환하려는 경우 `select` 절에 점 연산자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a34e-107">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="3a34e-108">예를 들어 각 `student`의 `ID`만 반환하려면 `select` 절을 다음과 같이 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34e-108">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```csharp  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="3a34e-109">예제</span><span class="sxs-lookup"><span data-stu-id="3a34e-109">Example</span></span>  

 <span data-ttu-id="3a34e-110">다음 예제에서는 무명 형식을 사용하여 지정된 조건과 일치하는 각 소스 요소의 속성 하위 집합만 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a34e-110">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 <span data-ttu-id="3a34e-111">이름이 지정되지 않은 경우 무명 형식은 소스 요소의 이름을 해당 속성에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34e-111">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="3a34e-112">무명 형식의 속성에 새 이름을 지정하려면 `select` 문을 다음과 같이 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34e-112">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```csharp  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="3a34e-113">앞의 예제에서 이 작업을 수행하는 경우 `Console.WriteLine` 문도 변경되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a34e-113">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a34e-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3a34e-114">Compiling the Code</span></span>  
  
<span data-ttu-id="3a34e-115">이 코드를 실행하려면 System.Linq에 대한 `using` 지시문을 통해 클래스를 복사하여 C# 콘솔 애플리케이션 프로젝트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3a34e-115">To run this code, copy and paste the class into a C# console application  with a `using` directive for System.Linq.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3a34e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a34e-116">See also</span></span>

- [<span data-ttu-id="3a34e-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3a34e-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3a34e-118">익명 형식</span><span class="sxs-lookup"><span data-stu-id="3a34e-118">Anonymous Types</span></span>](./anonymous-types.md)
- [<span data-ttu-id="3a34e-119">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="3a34e-119">LINQ in C#</span></span>](../../linq/index.md)
