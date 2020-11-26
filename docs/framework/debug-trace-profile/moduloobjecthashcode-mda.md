---
title: moduloObjectHashcode MDA
description: ModuloObjectHashcode MDA (관리 디버깅 도우미)를 검토 하 여 GetHashCode 메서드 결과의 나머지 값을 가져오도록 개체 클래스를 변경 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
ms.openlocfilehash: 6258d5df7be1923a69de3172dd4c7f32e0b51f35
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240526"
---
# <a name="moduloobjecthashcode-mda"></a><span data-ttu-id="5d1fb-103">moduloObjectHashcode MDA</span><span class="sxs-lookup"><span data-stu-id="5d1fb-103">moduloObjectHashcode MDA</span></span>

<span data-ttu-id="5d1fb-104">`moduloObjectHashcode` MDA(관리 디버깅 도우미)가 <xref:System.Object> 클래스의 동작을 변경하여 <xref:System.Object.GetHashCode%2A> 메서드에서 반환한 해시 코드에서 모듈로 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-104">The `moduloObjectHashcode` managed debugging assistant (MDA) changes the behavior of the <xref:System.Object> class to perform a modulo operation on the hash code returned by the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="5d1fb-105">이 MDA의 기본 모듈러스는 1이므로, <xref:System.Object.GetHashCode%2A>에서 모든 개체에 대해 0을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-105">The default modulus for this MDA is 1, which causes <xref:System.Object.GetHashCode%2A> to return 0 for all objects.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5d1fb-106">증상</span><span class="sxs-lookup"><span data-stu-id="5d1fb-106">Symptoms</span></span>  

 <span data-ttu-id="5d1fb-107">새로운 버전의 CLR(공용 언어 런타임)로 이동하고 나면 프로그램이 더 이상 올바르게 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-107">After moving to a new version of the common language runtime (CLR), a program no longer executes properly:</span></span>  
  
- <span data-ttu-id="5d1fb-108">프로그램이 <xref:System.Collections.Hashtable>에서 잘못된 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-108">The program is getting the wrong object from a <xref:System.Collections.Hashtable>.</span></span>  
  
- <span data-ttu-id="5d1fb-109"><xref:System.Collections.Hashtable>의 열거형 순서에 프로그램을 중단시키는 변경 내용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-109">The order of enumeration from a <xref:System.Collections.Hashtable> has a change that breaks the program.</span></span>  
  
- <span data-ttu-id="5d1fb-110">서로 같았던 두 개의 개체가 더 이상 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-110">Two objects that used to be equal are no longer equal.</span></span>  
  
- <span data-ttu-id="5d1fb-111">서로 같지 않았던 두 개의 개체가 이제 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-111">Two objects that used to not be equal are now equal.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5d1fb-112">원인</span><span class="sxs-lookup"><span data-stu-id="5d1fb-112">Cause</span></span>  

 <span data-ttu-id="5d1fb-113">키의 클래스에서 <xref:System.Object.Equals%2A> 메서드를 <xref:System.Collections.Hashtable>에 구현하면 <xref:System.Object.GetHashCode%2A> 메서드 호출 결과와 비교하여 개체의 동일성을 테스트하므로 프로그램이 <xref:System.Collections.Hashtable>에서 잘못된 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-113">Your program may be getting the wrong object from a <xref:System.Collections.Hashtable> because the implementation of the <xref:System.Object.Equals%2A> method on the class for the key into the <xref:System.Collections.Hashtable> tests for equality of objects by comparing the results of the call to the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="5d1fb-114">각 필드의 값이 서로 달라도 두 개체의 해시 코드는 동일할 수 있으므로 개체의 동일성을 테스트하는 데 해시 코드를 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-114">Hash codes should not be used to test for object equality because two objects may have the same hash code even if their respective fields have different values.</span></span> <span data-ttu-id="5d1fb-115">해시 코드 충돌은 실제로는 매우 드물지만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-115">These hash code collisions, although rare in practice, do occur.</span></span> <span data-ttu-id="5d1fb-116">이 경우 동일하지 않은 두 개의 키가 동일하게 표시되며 <xref:System.Collections.Hashtable>에서 잘못된 개체가 반환되는 식으로 <xref:System.Collections.Hashtable> 검색에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-116">The effect this has on a <xref:System.Collections.Hashtable> lookup is that two keys which are not equal appear to be equal, and the wrong object is returned from the <xref:System.Collections.Hashtable>.</span></span> <span data-ttu-id="5d1fb-117">성능상의 이유로 런타임 버전 간에 <xref:System.Object.GetHashCode%2A> 구현이 변경될 수 있으므로 한 버전에서 발생하지 않는 충돌이 후속 버전에서는 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-117">For performance reasons, the implementation of <xref:System.Object.GetHashCode%2A> can change between runtime versions, so collisions that might not occur on one version might occur on subsequent versions.</span></span> <span data-ttu-id="5d1fb-118">이 MDA를 사용하면 해시 코드가 충돌할 때 코드에 버그가 있는지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-118">Enable this MDA to test whether your code has bugs when hash codes collide.</span></span> <span data-ttu-id="5d1fb-119">이 MDA가 사용되면 <xref:System.Object.GetHashCode%2A> 메서드에서 0을 반환하므로, 모든 해시 코드 충돌의 원인이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-119">When enabled, this MDA causes the <xref:System.Object.GetHashCode%2A> method to return 0, resulting in all hash codes colliding.</span></span> <span data-ttu-id="5d1fb-120">이 MDA를 사용하면 프로그램 속도가 저하되는 영향만 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-120">The only effect enabling this MDA should have on your program is that your program runs slower.</span></span>  
  
 <span data-ttu-id="5d1fb-121">키의 해시 코드를 컴퓨팅하는 데 사용하는 알고리즘이 변경되면 <xref:System.Collections.Hashtable>의 열거형 순서가 런타임 버전 간 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-121">The order of enumeration from a <xref:System.Collections.Hashtable> may change from one version of the runtime to another if the algorithm used to compute the hash codes for the key change.</span></span> <span data-ttu-id="5d1fb-122">프로그램이 해시 테이블의 값 또는 키의 열거형 순서에 종속되는지 테스트하려면 이 MDA를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-122">To test whether your program has taken a dependency on the order of enumeration of keys or values out of a hash table, you can enable this MDA.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5d1fb-123">해결 방법</span><span class="sxs-lookup"><span data-stu-id="5d1fb-123">Resolution</span></span>  

 <span data-ttu-id="5d1fb-124">개체 ID의 대안으로 해시 코드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-124">Never use hash codes as a substitute for object identity.</span></span> <span data-ttu-id="5d1fb-125">해시 코드를 비교하지 않도록 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 메서드의 재정의를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-125">Implement the override of the <xref:System.Object.Equals%2A?displayProperty=nameWithType> method to not compare hash codes.</span></span>  
  
 <span data-ttu-id="5d1fb-126">해시 테이블에 있는 값 또는 키의 열거형 순서에 대한 종속성을 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-126">Do not create dependencies on the order of enumerations of keys or values in hash tables.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5d1fb-127">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="5d1fb-127">Effect on the Runtime</span></span>  

 <span data-ttu-id="5d1fb-128">이 MDA를 사용하면 애플리케이션이 더 느리게 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-128">Applications run more slowly when this MDA is enabled.</span></span> <span data-ttu-id="5d1fb-129">이 MDA에서는 반환된 해시 코드를 사용한 다음 모듈러스를 통해 나누는 경우 나머지를 대신 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-129">This MDA simply takes the hash code that would have been returned and instead returns the remainder when divided by a modulus.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5d1fb-130">출력</span><span class="sxs-lookup"><span data-stu-id="5d1fb-130">Output</span></span>  

 <span data-ttu-id="5d1fb-131">이 MDA에 대한 출력이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-131">There is no output for this MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="5d1fb-132">구성</span><span class="sxs-lookup"><span data-stu-id="5d1fb-132">Configuration</span></span>  

 <span data-ttu-id="5d1fb-133">`modulus` 특성을 통해 해시 코드에서 사용된 모듈러스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-133">The `modulus` attribute specifies the modulus used on the hash code.</span></span> <span data-ttu-id="5d1fb-134">기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="5d1fb-134">The default value is 1.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d1fb-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d1fb-135">See also</span></span>

- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5d1fb-136">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="5d1fb-136">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
