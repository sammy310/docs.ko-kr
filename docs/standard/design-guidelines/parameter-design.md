---
title: 매개 변수 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: KrzysztofCwalina
ms.openlocfilehash: 5a0f6e0fab5d0f2fe8574e348fc6b8ae726eeb99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757406"
---
# <a name="parameter-design"></a><span data-ttu-id="bc4ba-102">매개 변수 디자인</span><span class="sxs-lookup"><span data-stu-id="bc4ba-102">Parameter Design</span></span>
<span data-ttu-id="bc4ba-103">이 섹션에서는 매개 변수 디자인, 인수를 확인 하는 것에 대 한 지침을 사용 하 여 섹션을 비롯 한 광범위 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="bc4ba-104">에 설명 된 지침을 참조 해야 뿐만 [매개 변수 명명](../../../docs/standard/design-guidelines/naming-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="bc4ba-105">**✓ DO** 멤버에 필요한 기능을 제공 하는 최소 파생 된 매개 변수 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="bc4ba-106">예를 들어, 컬렉션을 열거 하 고 각 항목을 콘솔에 출력 하는 메서드를 디자인.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="bc4ba-107">이러한 메서드를 취해야 <xref:System.Collections.IEnumerable> 매개 변수로 되지 <xref:System.Collections.ArrayList> 또는 <xref:System.Collections.IList>예를 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="bc4ba-108">**X DO NOT** 예약 된 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="bc4ba-109">멤버에 대 한 추가 입력 이후 버전에서 필요한 경우에 새 오버 로드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="bc4ba-110">**X DO NOT** 가 공개적으로 포인터, 포인터, 배열 또는 다차원 배열을 매개 변수로 사용 하는 메서드를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="bc4ba-111">포인터 및 다차원 배열은 비교적 제대로 사용 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="bc4ba-112">대부분의 경우 Api 이러한 형식을 매개 변수로 방지 하기 위해 향후 재설계 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="bc4ba-113">**✓ DO** 모든 배치 `out` 다음 값으로의 모든 매개 변수 및 `ref` 매개 변수 (매개 변수 배열 제외) 매개 변수 오버 로드 간의 순서 지정에 불일치가 발생 하는 경우에 (참조 [멤버 오버 로드](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="bc4ba-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="bc4ba-114">`out` 메서드 시그니처를 더욱 쉽게 이해 함께 그룹화 하 고 추가 반환 값으로 매개 변수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="bc4ba-115">**✓ DO** 멤버를 재정의 하는 경우 매개 변수를 명명 또는 인터페이스 멤버 구현 일관 되 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="bc4ba-116">이 메서드 간의 관계를 더 잘 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="bc4ba-117">열거형 및 부울 매개 변수 중에서 선택</span><span class="sxs-lookup"><span data-stu-id="bc4ba-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="bc4ba-118">**✓ DO** 구성원 부울 매개 변수 두 개 이상의 미칠 경우 열거형을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="bc4ba-119">**X DO NOT** 확실히 될 수 없으므로 두 개 이상의 값에 대 한 필요 하지 않는 한 부울을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="bc4ba-120">열거형 값을 이후 추가할 수 있는 공간을 제공 하지만에서 설명 하는 열거형 값을 추가 하는 모든 의미 고려해 야 [열거형 디자인](../../../docs/standard/design-guidelines/enum.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="bc4ba-121">**✓ CONSIDER** 부울 값이 실제로 두 가지 상태는 부울 속성을 초기화 하는 생성자 매개 변수를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="bc4ba-122">인수 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="bc4ba-122">Validating Arguments</span></span>  
 <span data-ttu-id="bc4ba-123">**✓ DO** public, protected 또는 명시적으로 구현 된 멤버에 전달 되는 인수의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="bc4ba-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, 또는 해당 서브 클래스 중 하나를 유효성 검사에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="bc4ba-125">없는 실제 유효성 검사를 반드시 public 또는 protected 멤버 자체에서 발생 하는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="bc4ba-126">일부 private 또는 internal 루틴에서 하위 수준에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="bc4ba-127">중요 한 점은 최종 사용자에 게 노출 되는 전체 화면 영역에서 인수를 검사 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="bc4ba-128">**✓ DO** throw <xref:System.ArgumentNullException> 에 null 인수가 전달 되 고 멤버가 null 인수를 지원 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="bc4ba-129">**✓ DO** enum 매개 변수 유효성 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="bc4ba-130">열거형 인수가 열거형으로 정의 된 범위에 있을 것을 가정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="bc4ba-131">CLR 값을 열거형에 정의 되지 않은 경우에 모든 정수 값 열거형 값으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="bc4ba-132">**X DO NOT** 사용 <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> 열거형 범위 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="bc4ba-133">**✓ DO** 유효성을 검사 한 후 인수가 변경할 수 있는 변경 수에 유의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="bc4ba-134">멤버는 중요 한 보안을 모르는 경우 복사본 및 다음 유효성 검사 및 인수를 처리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="bc4ba-135">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="bc4ba-135">Parameter Passing</span></span>  
 <span data-ttu-id="bc4ba-136">프레임 워크 디자이너의 관점에서 그룹이 세 가지 주요 매개 변수: by 값 매개 변수 `ref` 매개 변수 및 `out` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="bc4ba-137">인수 값으로 매개 변수를 통해 전달 되 면 멤버에 전달 된 실제 인수의 복사본을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="bc4ba-138">인수 값 형식이 면 인수의 복사본이 스택에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="bc4ba-139">인수가 참조 형식이 면 참조의 복사본이 스택에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="bc4ba-140">가장 인기 있는 CLR 언어와 같은 C#, VB.NET 및 C++를 기본적으로 매개 변수 값으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="bc4ba-141">인수로 전달 되는 경우는 `ref` 매개 변수를 멤버에 전달 된 실제 인수에 대 한 참조를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="bc4ba-142">인수 값 형식이 면 인수에 대 한 참조를 스택에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="bc4ba-143">인수가 참조 형식이 면 참조에 대 한 참조를 스택에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="bc4ba-144">`Ref` 호출자에 의해 전달 된 인수를 수정 하려면 멤버 수 있도록 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="bc4ba-145">`Out` 매개 변수는 유사한 `ref` 매개 변수를 약간 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="bc4ba-146">매개 변수가 처음 것으로 간주 되어 할당 되지 않은 일부 값을 할당 하기 전에 멤버 본문에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="bc4ba-147">또한 매개 변수 멤버를 반환 하기 전에 일부 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="bc4ba-148">**X AVOID** 를 사용 하 여 `out` 또는 `ref` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="bc4ba-149">사용 하 여 `out` 또는 `ref` 매개 변수는 포인터를 값 형식과 참조 형식이 어떻게를 이해 하 고 여러 개의 반환 값을 사용 하 여 메서드를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="bc4ba-150">간의 차이 뿐만 `out` 고 `ref` 매개 변수는 잘 알려져 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="bc4ba-151">마스터 작업에 사용자가 일반 사용자를 대상에 대 한 디자인 하는 프레임 워크 설계자를 기대할 수 없습니다 `out` 또는 `ref` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="bc4ba-152">**X DO NOT** 참조 형식을 참조로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="bc4ba-153">참조를 바꿔 사용할 수 있는 메서드와 같은 규칙으로 제한 된 몇 가지 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="bc4ba-154">가변 개수의 매개 변수를 사용 하 여 멤버</span><span class="sxs-lookup"><span data-stu-id="bc4ba-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="bc4ba-155">가변 개수의 인수를 사용할 수 있는 멤버 배열 매개 변수에 제공 하 여 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="bc4ba-156">예를 들어 <xref:System.String> 다음 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="bc4ba-157">사용자를 호출할 수는 <xref:System.String.Format%2A?displayProperty=nameWithType> 메서드를 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="bc4ba-158">배열 매개 변수에 C# params 키워드를 추가 소위 매개 변수 배열 매개 변수에 매개 변수를 변경 하 고 임시 배열을 만드는 바로 가기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="bc4ba-159">이렇게 하면 배열 요소를 인수 목록에서 직접 전달 하 여 메서드를 호출 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="bc4ba-160">참고 매개 변수 목록의 마지막 매개 변수에 params 키워드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="bc4ba-161">**✓ CONSIDER** 는 적은 수의 요소 배열을 전달 하는 최종 사용자가 예상 되는 경우에 params 키워드 배열 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="bc4ba-162">예상 하지만 많은 요소 전달할 공통 시나리오, 사용자가 이러한 요소를 인라인으로, 전달 되지 않을 수 있습니다 하 고 params 키워드 이므로 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="bc4ba-163">**X AVOID** 호출자에 게는 거의 항상 이미 입력 배열의 경우 매개 변수 배열을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="bc4ba-164">예를 들어, 바이트 배열 매개 변수를 사용 하 여 멤버 개별 바이트를 전달 하 여 호출 됩니다 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="bc4ba-165">이러한 이유로.NET Framework의 바이트 배열 매개 변수는 params 키워드를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="bc4ba-166">**X DO NOT** 배열 멤버 params 배열 매개 변수를 사용 하 여 수정 된 경우 매개 변수 배열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="bc4ba-167">대부분의 컴파일러 호출 사이트에서 임시 배열로 멤버에 대 한 인수를 사용 하는 사실 때문에 배열 임시 개체 일 수 있습니다 및 배열에 대 한 수정은 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="bc4ba-168">**✓ CONSIDER** 단순 오버 로드에서에 params 키워드를 사용 하 여 경우에 더 복잡 한 오버 로드를 사용 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="bc4ba-169">사용자는 모든 오버 로드의 경우에 매개 변수 배열을 하나의 오버 로드에 있는 값 경우 직접 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="bc4ba-170">**✓ DO** params 키워드를 사용할 수 있도록 적절 한 매개 변수를 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="bc4ba-171">**✓ CONSIDER** 적은 수의 성능에 민감한 매우 Api에는 인수를 사용 하 여 호출에 대 한 특별 한 오버 로드와 코드 경로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="bc4ba-172">이렇게 하면 적은 수의 인수를 사용 하 여 API를 호출할 때 배열 개체를 만들지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="bc4ba-173">배열 매개 변수의 단 수 형태를 가져오고 숫자 접미사를 추가 하 여 매개 변수의 이름이 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="bc4ba-174">특별 한 경우 전체 코드 경로 배열을 만듭니다 뿐 아니라 한 보다 일반적인 메서드를 호출 하려는 경우에 다음이 수행만 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="bc4ba-175">**✓ DO** 유의 매개 변수 배열 인수는 null을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="bc4ba-176">배열의 처리 하기 전에 null 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="bc4ba-177">**X DO NOT** 사용는 `varargs` 메서드, 줄임표 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="bc4ba-178">일부 CLR 언어와 같은 C++를 호출 하는 가변 매개 변수 목록을 전달 하는 것에 대 한 대체는 규칙을 지원 `varargs` 메서드.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="bc4ba-179">CLS 규격이 아니므로 프레임 워크에서 규칙을 해야 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="bc4ba-180">포인터 매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc4ba-180">Pointer Parameters</span></span>  
 <span data-ttu-id="bc4ba-181">일반적으로 포인터 하지 잘 설계 된 관리 코드 프레임 워크는 공개 노출 영역에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="bc4ba-182">대부분의 경우 포인터를 캡슐화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="bc4ba-183">그러나 포인터는 상호 운용성을 위해 필요한 경우에 따라 및 포인터를 사용 하 여 이러한 사례에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="bc4ba-184">**✓ DO** 포인터 CLS 규격이 아닙니다. 때문에 포인터 인수를 사용 하는 멤버에 대 한 대체 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="bc4ba-185">**X AVOID** 과도 한 인수 포인터 인수의 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="bc4ba-186">**✓ DO** 포인터로 멤버를 디자인 하는 경우 일반 포인터와 관련 된 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="bc4ba-187">예를 들어, 간단한 포인터 산술 연산은 동일한 결과 얻는 데 사용할 수 있으므로 시작 인덱스를 전달할 필요가 없습니다 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4ba-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="bc4ba-188">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="bc4ba-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bc4ba-189">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="bc4ba-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc4ba-190">참고자료</span><span class="sxs-lookup"><span data-stu-id="bc4ba-190">See also</span></span>

- [<span data-ttu-id="bc4ba-191">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="bc4ba-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="bc4ba-192">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="bc4ba-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
