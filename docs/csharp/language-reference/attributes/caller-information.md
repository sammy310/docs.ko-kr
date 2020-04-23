---
title: 'C# 예약된 특성: 호출자 정보 추적'
ms.date: 04/09/2020
description: 이 특성은 멤버를 호출하는 코드에 대한 정보를 생성하도록 컴파일러에 지시합니다. CallerFilePath, CallerLineNumber 및 CallerMemberName을 사용하여 자세한 추적 정보를 제공합니다.
ms.openlocfilehash: ee061d4cae35bdcc0b89007e360e94fee8c5f87c
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389825"
---
# <a name="reserved-attributes-determine-caller-information"></a><span data-ttu-id="31754-104">예약된 특성: 호출자 정보 확인</span><span class="sxs-lookup"><span data-stu-id="31754-104">Reserved attributes: Determine caller information</span></span>

<span data-ttu-id="31754-105">정보 특성을 사용하여 메서드 호출자에 대한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31754-105">Using info attributes, you obtain information about the caller to a method.</span></span> <span data-ttu-id="31754-106">소스 코드 파일 경로, 소스 코드 줄 번호 및 호출자의 멤버 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31754-106">You obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="31754-107">멤버 호출자 정보를 얻으려면 선택적 매개 변수에 적용되는 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="31754-107">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="31754-108">각 선택적 매개 변수는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31754-108">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="31754-109">다음 표에서는 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 네임스페이스에 정의된 호출자 정보 특성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="31754-109">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="31754-110">특성</span><span class="sxs-lookup"><span data-stu-id="31754-110">Attribute</span></span>|<span data-ttu-id="31754-111">설명</span><span class="sxs-lookup"><span data-stu-id="31754-111">Description</span></span>|<span data-ttu-id="31754-112">형식</span><span class="sxs-lookup"><span data-stu-id="31754-112">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="31754-113">호출자를 포함한 소스 파일의 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="31754-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="31754-114">전체 경로는 컴파일 시간의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="31754-114">The full path is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="31754-115">메서드가 호출되는 소스 파일의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="31754-115">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="31754-116">호출자의 메서드 이름 또는 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="31754-116">Method name or property name of the caller.</span></span>|`String`|

<span data-ttu-id="31754-117">이 정보는 추적, 디버깅을 작성하고 진단 도구를 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31754-117">This information helps you write tracing, debugging, and create diagnostic tools.</span></span> <span data-ttu-id="31754-118">다음 예제에서는 호출자 정보 특성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31754-118">The following example shows how to use caller info attributes.</span></span> <span data-ttu-id="31754-119">`TraceMessage` 메서드에 대한 각 호출에서 호출자 정보는 선택적 매개 변수에 대한 인수로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="31754-119">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [CallerMemberName] string memberName = "",
        [CallerFilePath] string sourceFilePath = "",
        [CallerLineNumber] int sourceLineNumber = 0)
{
    Trace.WriteLine("message: " + message);
    Trace.WriteLine("member name: " + memberName);
    Trace.WriteLine("source file path: " + sourceFilePath);
    Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

<span data-ttu-id="31754-120">각각의 선택적 매개 변수에 대한 명시적 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31754-120">You specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="31754-121">선택적 매개 변수로 지정되지 않은 매개 변수에 호출자 정보 특성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31754-121">You can't apply caller info attributes to parameters that aren't specified as optional.</span></span> <span data-ttu-id="31754-122">호출자 정보 특성은 매개 변수를 선택적 매개 변수로 만들지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="31754-122">The caller info attributes don't make a parameter optional.</span></span> <span data-ttu-id="31754-123">대신, 이런 특성은 인수가 생략될 때 전달되는 기본값에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="31754-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span> <span data-ttu-id="31754-124">호출자 정보 값은 컴파일 시간에 리터럴로 중간 언어(IL) 내로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="31754-124">Caller info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="31754-125">예외에 대한 <xref:System.Exception.StackTrace%2A> 속성의 결과와 달리 결과가 난독화의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31754-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span> <span data-ttu-id="31754-126">선택적 인수를 명시적으로 제공하여 호출자 정보를 제어하거나 호출자 정보를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31754-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

### <a name="member-names"></a><span data-ttu-id="31754-127">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="31754-127">Member names</span></span>

<span data-ttu-id="31754-128">`CallerMemberName` 특성을 사용하여 멤버 이름을 호출된 메서드에 대한 `String` 인수로 지정하는 것을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31754-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="31754-129">이 기술을 사용하여 **이름 바꾸기 리팩터링**이 `String` 값을 변경하지 못하는 문제를 피합니다.</span><span class="sxs-lookup"><span data-stu-id="31754-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="31754-130">이 이점은 다음 작업에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="31754-130">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="31754-131">추적 및 진단 루틴 사용.</span><span class="sxs-lookup"><span data-stu-id="31754-131">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="31754-132">데이터를 바인딩할 때 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스 구현.</span><span class="sxs-lookup"><span data-stu-id="31754-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="31754-133">이 인터페이스에서는 컨트롤에서 업데이트된 정보를 표시할 수 있도록 바운드 컨트롤의 속성이 변경되었음을 알리는 개체의 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31754-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="31754-134">`CallerMemberName` 특성이 없으면 속성 이름을 리터럴로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31754-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="31754-135">아래 차트는 `CallerMemberName` 특성을 사용할 때 반환되는 멤버 이름을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="31754-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>

|<span data-ttu-id="31754-136">호출 발생 범위</span><span class="sxs-lookup"><span data-stu-id="31754-136">Calls occur within</span></span>|<span data-ttu-id="31754-137">멤버 이름 결과</span><span class="sxs-lookup"><span data-stu-id="31754-137">Member name result</span></span>|
|-|-|
|<span data-ttu-id="31754-138">메서드, 속성 또는 이벤트</span><span class="sxs-lookup"><span data-stu-id="31754-138">Method, property, or event</span></span>|<span data-ttu-id="31754-139">호출에서 시작한 메서드, 속성 또는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="31754-139">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="31754-140">생성자</span><span class="sxs-lookup"><span data-stu-id="31754-140">Constructor</span></span>|<span data-ttu-id="31754-141">".ctor" 문자열</span><span class="sxs-lookup"><span data-stu-id="31754-141">The string ".ctor"</span></span>|
|<span data-ttu-id="31754-142">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="31754-142">Static constructor</span></span>|<span data-ttu-id="31754-143">".cctor" 문자열</span><span class="sxs-lookup"><span data-stu-id="31754-143">The string ".cctor"</span></span>|
|<span data-ttu-id="31754-144">소멸자</span><span class="sxs-lookup"><span data-stu-id="31754-144">Destructor</span></span>|<span data-ttu-id="31754-145">"Finalize" 문자열</span><span class="sxs-lookup"><span data-stu-id="31754-145">The string "Finalize"</span></span>|
|<span data-ttu-id="31754-146">사용자 정의 연산자 또는 변환</span><span class="sxs-lookup"><span data-stu-id="31754-146">User-defined operators or conversions</span></span>|<span data-ttu-id="31754-147">멤버에 대해 생성되는 이름입니다(예: "op_Addition").</span><span class="sxs-lookup"><span data-stu-id="31754-147">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="31754-148">특성 생성자</span><span class="sxs-lookup"><span data-stu-id="31754-148">Attribute constructor</span></span>|<span data-ttu-id="31754-149">특성이 적용되는 메서드 또는 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="31754-149">The name of the method or property to which the attribute is applied.</span></span> <span data-ttu-id="31754-150">특성이 멤버 내에 있는 어떤 요소인 경우(예: 매개 변수, 반환 값 또는 제네릭 형식 매개 변수) 이 결과는 그 요소와 관련된 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="31754-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="31754-151">포함하는 멤버가 없음(예: 어셈블리 수준 또는 형식에 적용되는 특성)</span><span class="sxs-lookup"><span data-stu-id="31754-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="31754-152">선택적 매개 변수의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="31754-152">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="31754-153">참조</span><span class="sxs-lookup"><span data-stu-id="31754-153">See also</span></span>

- [<span data-ttu-id="31754-154">명명된 인수 및 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="31754-154">Named and Optional Arguments</span></span>](../../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="31754-155">특성</span><span class="sxs-lookup"><span data-stu-id="31754-155">Attributes</span></span>](../../../standard/attributes/index.md)
