---
title: 추적 스위치
description: 추적 출력을 활성화, 비활성화 및 필터링 할 수 있는 추적 스위치를 탐색 합니다. .NET에서는 BooleanSwitch, TraceSwitch 및 SourceSwitch 클래스를 제공 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], trace switches
- trace switches, about trace switches
- tracing [.NET Framework], level of detail
- switches, trace
- trace switches
- trace switches, creating custom
ms.assetid: 8ab913aa-f400-4406-9436-f45bc6e54fbe
ms.openlocfilehash: dfbff0a78b3c6c1318224ccc9608c1b816f9d5f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238056"
---
# <a name="trace-switches"></a><span data-ttu-id="e5b37-104">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="e5b37-104">Trace Switches</span></span>

<span data-ttu-id="e5b37-105">추적 스위치를 사용하여 추적 출력을 활성화, 비활성화 및 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-105">Trace switches enable you to enable, disable, and filter tracing output.</span></span> <span data-ttu-id="e5b37-106">코드에 존재하며 .config 파일을 통해 외부에서 구성할 수 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-106">They are objects that exist in your code and can be configured externally through the .config file.</span></span> <span data-ttu-id="e5b37-107">.NET Framework에서 제공되는 세 가지 유형의 추적 스위치( <xref:System.Diagnostics.BooleanSwitch> 클래스, <xref:System.Diagnostics.TraceSwitch> 클래스 및 <xref:System.Diagnostics.SourceSwitch> 클래스)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-107">There are three types of trace switches provided in the .NET Framework: the <xref:System.Diagnostics.BooleanSwitch> class, the <xref:System.Diagnostics.TraceSwitch> class, and the <xref:System.Diagnostics.SourceSwitch> class.</span></span> <span data-ttu-id="e5b37-108"><xref:System.Diagnostics.BooleanSwitch> 클래스는 다양한 trace 문을 사용하거나 사용하지 않도록 설정하는 토글 스위치 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-108">The <xref:System.Diagnostics.BooleanSwitch> class acts as a toggle switch, either enabling or disabling a variety of trace statements.</span></span> <span data-ttu-id="e5b37-109"><xref:System.Diagnostics.TraceSwitch> 및 <xref:System.Diagnostics.SourceSwitch> 클래스를 통해 특정 추적 수준에 대한 추적 스위치를 사용하도록 설정하여 해당 수준 및 그 아래의 모든 수준에 대해 지정된 <xref:System.Diagnostics.Trace> 또는 <xref:System.Diagnostics.TraceSource> 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-109">The <xref:System.Diagnostics.TraceSwitch> and <xref:System.Diagnostics.SourceSwitch> classes allow you to enable a trace switch for a particular tracing level so that the <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.TraceSource> messages specified for that level and all levels below it appear.</span></span> <span data-ttu-id="e5b37-110">스위치를 사용하지 않도록 설정하면 추적 메시지가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-110">If you disable the switch, the trace messages will not appear.</span></span> <span data-ttu-id="e5b37-111">이러한 모든 클래스는 사용자 개발 스위치와 마찬가지로 추상(**MustInherit**) 클래스 **Switch** 에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-111">All these classes derive from the abstract (**MustInherit**) class **Switch**, as should any user-developed switches.</span></span>  
  
 <span data-ttu-id="e5b37-112">추적 스위치는 정보를 필터링하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-112">Trace switches can be useful for filtering information.</span></span> <span data-ttu-id="e5b37-113">예를 들어 데이터 액세스 모듈에서는 모든 추적 메시지가 표시되고 애플리케이션의 나머지 부분에서는 오류 메시지만 표시되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-113">For example, you might want to see every tracing message in a data access module, but only error messages in the rest of the application.</span></span> <span data-ttu-id="e5b37-114">이 경우 데이터 액세스 모듈에 대해 하나의 추적 스위치를 사용하고 애플리케이션의 나머지 부분에 대해 하나의 스위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-114">In that case, you would use one trace switch for the data access module and one switch for the rest of the application.</span></span> <span data-ttu-id="e5b37-115">.config 파일을 사용하여 스위치를 적절한 설정으로 구성하면 수신하는 추적 메시지 유형을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-115">By using the .config file to configure the switches to the appropriate settings, you could control what types of trace message you received.</span></span> <span data-ttu-id="e5b37-116">자세한 내용은 [방법: 추적 스위치 만들기, 초기화 및 구성](how-to-create-initialize-and-configure-trace-switches.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5b37-116">For more information, see [How to: Create, Initialize and Configure Trace Switches](how-to-create-initialize-and-configure-trace-switches.md).</span></span>  
  
 <span data-ttu-id="e5b37-117">일반적으로 배포된 애플리케이션은 애플리케이션 실행 시 화면에 나타나거나 로그 파일에 채워지는 여러 관련 없는 추적 메시지를 사용자가 관찰할 필요가 없도록 스위치를 사용할 수 없는 상태로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-117">Typically, a deployed application is executed with its switches disabled, so that users need not observe a lot of irrelevant trace messages appearing on a screen or filling up a log file as the application runs.</span></span> <span data-ttu-id="e5b37-118">애플리케이션 실행 중에 문제가 발생할 경우 애플리케이션을 중지하고 스위치를 사용하도록 설정한 다음 애플리케이션을 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-118">If a problem arises during application execution, you can stop the application, enable the switches, and restart the application.</span></span> <span data-ttu-id="e5b37-119">그러면 추적 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-119">Then the tracing messages will be displayed.</span></span>  
  
 <span data-ttu-id="e5b37-120">스위치를 사용하려면 먼저 **BooleanSwitch** 클래스, **TraceSwitch** 클래스 또는 개발자 정의 스위치 클래스에서 스위치 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-120">To use a switch you must first create a switch object from a **BooleanSwitch** class, a **TraceSwitch** class, or a developer-defined switch class.</span></span> <span data-ttu-id="e5b37-121">개발자 정의 스위치를 만드는 방법에 대한 자세한 내용은 .NET Framework 참조에서 <xref:System.Diagnostics.Switch> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5b37-121">For more information about creating developer-defined switches, see the <xref:System.Diagnostics.Switch> class in the .NET Framework reference.</span></span> <span data-ttu-id="e5b37-122">스위치 개체를 사용할 시기를 지정하는 구성 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-122">Then you set a configuration value that specifies when the switch object is to be used.</span></span> <span data-ttu-id="e5b37-123">그런 후에 다양한 **추적** (또는 **디버그**) 추적 메서드에서 스위치 개체의 설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-123">You then test the setting of the switch object in various **Trace** (or **Debug**) tracing methods.</span></span>  
  
## <a name="trace-levels"></a><span data-ttu-id="e5b37-124">추적 수준</span><span class="sxs-lookup"><span data-stu-id="e5b37-124">Trace Levels</span></span>  

 <span data-ttu-id="e5b37-125">**TraceSwitch** 를 사용하는 경우 추가로 고려해야 할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-125">When you use **TraceSwitch**, there are additional considerations.</span></span> <span data-ttu-id="e5b37-126">**TraceSwitch** 개체에는 스위치가 특정 수준 이상으로 설정되었는지 여부를 나타내는 **부울** 값을 반환하는 다음 4가지 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-126">A **TraceSwitch** object has four properties that return **Boolean** values indicating whether the switch is set to at least a particular level:</span></span>  
  
- <xref:System.Diagnostics.TraceSwitch.TraceError%2A?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceSwitch.TraceWarning%2A?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceSwitch.TraceInfo%2A?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceSwitch.TraceVerbose%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="e5b37-127">수준을 통해 수신하는 추적 정보의 양을 문제 해결에 필요한 정보로만 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-127">Levels allow you to limit the amount of tracing information you receive to only that information needed to solve a problem.</span></span> <span data-ttu-id="e5b37-128">추적 스위치를 적절한 추적 수준으로 설정하고 구성하여 추적 출력에 표시할 세부 정보 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-128">You specify the level of detail you want in your tracing output by setting and configuring trace switches to the appropriate trace level.</span></span> <span data-ttu-id="e5b37-129">오류 메시지, 경고 메시지, 정보 메시지, 자세한 추적 메시지를 수신하거나 메시지를 수신하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-129">You can receive error messages, warning messages, informational messages, verbose tracing messages, or no message at all.</span></span>  
  
 <span data-ttu-id="e5b37-130">각 수준에 연결할 메시지 종류는 전적으로 사용자가 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-130">It is entirely up to you to decide what kind of message to associate with each level.</span></span> <span data-ttu-id="e5b37-131">일반적으로 추적 메시지의 내용은 각 수준에 연결하는 항목에 따라 달라지지만 수준 간의 차이를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-131">Typically, the content of tracing messages depends on what you associate with each level, but you determine the differences between levels.</span></span> <span data-ttu-id="e5b37-132">예를 들어 수준 3(**Info**)에서는 문제에 대한 자세한 설명을 제공하지만 수준 1(**Error**)에서는 오류 참조 번호만 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-132">You might want to provide detailed descriptions of a problem at level 3 (**Info**), for example, but provide only an error reference number at level 1 (**Error**).</span></span> <span data-ttu-id="e5b37-133">애플리케이션에 가장 적합한 체계는 전적으로 사용자가 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-133">It is entirely up to you to decide what scheme works best in your application.</span></span>  
  
 <span data-ttu-id="e5b37-134">이러한 속성은 **TraceLevel** 열거형의 값 1-4에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-134">These properties correspond to the values 1 through 4 of the **TraceLevel** enumeration.</span></span> <span data-ttu-id="e5b37-135">다음 표에서는 **TraceLevel** 열거형의 수준 및 해당 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-135">The following table lists the levels of the **TraceLevel** enumeration and their values.</span></span>  
  
|<span data-ttu-id="e5b37-136">열거형 값</span><span class="sxs-lookup"><span data-stu-id="e5b37-136">Enumerated value</span></span>|<span data-ttu-id="e5b37-137">정수 값</span><span class="sxs-lookup"><span data-stu-id="e5b37-137">Integer value</span></span>|<span data-ttu-id="e5b37-138">표시(또는 지정된 출력 대상에 기록)되는 메시지 유형</span><span class="sxs-lookup"><span data-stu-id="e5b37-138">Type of message displayed (or written to a specified output target)</span></span>|  
|----------------------|-------------------|---------------------------------------------------------------------------|  
|<span data-ttu-id="e5b37-139">끄기</span><span class="sxs-lookup"><span data-stu-id="e5b37-139">Off</span></span>|<span data-ttu-id="e5b37-140">0</span><span class="sxs-lookup"><span data-stu-id="e5b37-140">0</span></span>|<span data-ttu-id="e5b37-141">없음</span><span class="sxs-lookup"><span data-stu-id="e5b37-141">None</span></span>|  
|<span data-ttu-id="e5b37-142">Error</span><span class="sxs-lookup"><span data-stu-id="e5b37-142">Error</span></span>|<span data-ttu-id="e5b37-143">1</span><span class="sxs-lookup"><span data-stu-id="e5b37-143">1</span></span>|<span data-ttu-id="e5b37-144">오류 메시지만</span><span class="sxs-lookup"><span data-stu-id="e5b37-144">Only error messages</span></span>|  
|<span data-ttu-id="e5b37-145">경고</span><span class="sxs-lookup"><span data-stu-id="e5b37-145">Warning</span></span>|<span data-ttu-id="e5b37-146">2</span><span class="sxs-lookup"><span data-stu-id="e5b37-146">2</span></span>|<span data-ttu-id="e5b37-147">경고 메시지와 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="e5b37-147">Warning messages and error messages</span></span>|  
|<span data-ttu-id="e5b37-148">정보</span><span class="sxs-lookup"><span data-stu-id="e5b37-148">Info</span></span>|<span data-ttu-id="e5b37-149">3</span><span class="sxs-lookup"><span data-stu-id="e5b37-149">3</span></span>|<span data-ttu-id="e5b37-150">정보 메시지, 경고 메시지 및 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="e5b37-150">Informational messages, warning messages, and error messages</span></span>|  
|<span data-ttu-id="e5b37-151">자세히</span><span class="sxs-lookup"><span data-stu-id="e5b37-151">Verbose</span></span>|<span data-ttu-id="e5b37-152">4</span><span class="sxs-lookup"><span data-stu-id="e5b37-152">4</span></span>|<span data-ttu-id="e5b37-153">자세한 메시지, 정보 메시지, 경고 메시지 및 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="e5b37-153">Verbose messages, informational messages, warning messages, and error messages</span></span>|  
  
 <span data-ttu-id="e5b37-154">**TraceSwitch** 속성은 스위치에 대한 최대 추적 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-154">The **TraceSwitch** properties indicate the maximum trace level for the switch.</span></span> <span data-ttu-id="e5b37-155">즉, 지정된 수준 및 모든 하위 수준에 대한 추적 정보가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-155">That is, tracing information is written for the level specified as well as for all lower levels.</span></span> <span data-ttu-id="e5b37-156">예를 들어 **TraceInfo** 가 **true** 이면 **TraceError** 및 **TraceWarning** 도 **true** 이지만 **TraceVerbose** 는 **false** 가 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-156">For example, if **TraceInfo** is **true**, then **TraceError** and **TraceWarning** are also **true** but **TraceVerbose** might well be **false**.</span></span>  
  
 <span data-ttu-id="e5b37-157">이러한 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-157">These properties are read-only.</span></span> <span data-ttu-id="e5b37-158">**TraceLevel** 속성이 설정될 때 **TraceSwitch** 개체가 자동으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-158">The **TraceSwitch** object automatically sets them when the **TraceLevel** property is set.</span></span> <span data-ttu-id="e5b37-159">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-159">For example:</span></span>  
  
```vb  
Dim myTraceSwitch As New TraceSwitch("SwitchOne", "The first switch")  
myTraceSwitch.Level = TraceLevel.Info  
' This message box displays true, because setting the level to  
' TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString())  
' This messagebox displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString())  
```  
  
```csharp  
System.Diagnostics.TraceSwitch myTraceSwitch =
   new System.Diagnostics.TraceSwitch("SwitchOne", "The first switch");  
myTraceSwitch.Level = System.Diagnostics.TraceLevel.Info;  
// This message box displays true, because setting the level to
// TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString());  
// This message box displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString());  
```  
  
## <a name="developer-defined-switches"></a><span data-ttu-id="e5b37-160">개발자 정의 스위치</span><span class="sxs-lookup"><span data-stu-id="e5b37-160">Developer-Defined Switches</span></span>  

 <span data-ttu-id="e5b37-161">**BooleanSwitch** 및 **TraceSwitch** 를 제공하는 것 외에도 **Switch** 클래스에서 상속하고 기본 클래스 메서드를 사용자 지정 메서드로 재정의하여 고유한 스위치를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b37-161">In addition to providing **BooleanSwitch** and **TraceSwitch**, you can define your own switches by inheriting from the **Switch** class and overriding the base class methods with customized methods.</span></span> <span data-ttu-id="e5b37-162">개발자 정의 스위치를 만드는 방법에 대한 자세한 내용은 .NET Framework 참조에서 <xref:System.Diagnostics.Switch> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5b37-162">For more information about creating developer-defined switches, see the <xref:System.Diagnostics.Switch> class in the .NET Framework reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b37-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5b37-163">See also</span></span>

- [<span data-ttu-id="e5b37-164">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="e5b37-164">Trace Listeners</span></span>](trace-listeners.md)
- [<span data-ttu-id="e5b37-165">방법: 애플리케이션 코드에 Trace 문 추가</span><span class="sxs-lookup"><span data-stu-id="e5b37-165">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="e5b37-166">애플리케이션 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="e5b37-166">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
