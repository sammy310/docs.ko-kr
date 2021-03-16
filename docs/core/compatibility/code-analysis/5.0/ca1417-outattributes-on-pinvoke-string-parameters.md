---
title: '호환성이 손상되는 변경: CA1417: P/Invoke에 대한 문자열 매개 변수의 OutAttribute'
description: 코드 분석 규칙 CA1417 사용으로 발생하는 .NET 5의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/29/2020
ms.openlocfilehash: 74aa6dc867bc1eb62e32dd086dd6b43f62e7f01f
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257832"
---
# <a name="warning-ca1417-outattribute-on-string-parameter-for-pinvoke"></a><span data-ttu-id="0d405-103">경고 CA1417: P/Invoke에 대한 문자열 매개 변수의 OutAttribute</span><span class="sxs-lookup"><span data-stu-id="0d405-103">Warning CA1417: OutAttribute on string parameter for P/Invoke</span></span>

<span data-ttu-id="0d405-104">.NET 코드 분석기 규칙 [CA1417](/visualstudio/code-quality/ca1417)은 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-104">.NET code analyzer rule [CA1417](/visualstudio/code-quality/ca1417) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="0d405-105"><xref:System.String> 매개 변수가 값으로 전달되고 <xref:System.Runtime.InteropServices.OutAttribute>로 표시된 [P/Invoke(플랫폼 호출)](../../../../standard/native-interop/pinvoke.md) 메서드 정의에 대해 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-105">It produces a build warning for any [Platform Invoke (P/Invoke)](../../../../standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is passed by value and marked with <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

## <a name="change-description"></a><span data-ttu-id="0d405-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="0d405-106">Change description</span></span>

<span data-ttu-id="0d405-107">.NET 5부터 .NET SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="0d405-108">[CA1417](/visualstudio/code-quality/ca1417)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-108">Several of these rules are enabled, by default, including [CA1417](/visualstudio/code-quality/ca1417).</span></span> <span data-ttu-id="0d405-109">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="0d405-110">규칙 CA1417은 <xref:System.String> 매개 변수가 <xref:System.Runtime.InteropServices.OutAttribute> 특성으로 표시되고 값으로 전달된 [P/Invoke](../../../../standard/native-interop/pinvoke.md) 메서드 정의를 플래그로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-110">Rule CA1417 flags [P/Invoke](../../../../standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is marked with the <xref:System.Runtime.InteropServices.OutAttribute> attribute and is passed by value.</span></span> <span data-ttu-id="0d405-111">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="0d405-111">For example:</span></span>

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

<span data-ttu-id="0d405-112">.NET 런타임은 특정 프로그램에서 고유한 각 리터럴 문자열에 대한 단일 참조를 포함하는 인턴 풀이라는 테이블을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-112">The .NET runtime maintains a table, called the intern pool, that contains a single reference to each unique literal string in a program.</span></span> <span data-ttu-id="0d405-113"><xref:System.Runtime.InteropServices.OutAttribute>로 표시된 인터닝된 문자열이 P/Invoke 메서드에 숫자로 전달되는 경우 런타임은 불안정해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-113">If an interned string marked with <xref:System.Runtime.InteropServices.OutAttribute> is passed by value to a P/Invoke method, the runtime can be destabilized.</span></span> <span data-ttu-id="0d405-114">문자열 인터닝에 대한 자세한 내용은 <xref:System.String.Intern(System.String)?displayProperty=nameWithType>에 대한 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d405-114">For more information about string interning, see the remarks for <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="0d405-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0d405-115">Version introduced</span></span>

<span data-ttu-id="0d405-116">5.0</span><span class="sxs-lookup"><span data-stu-id="0d405-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0d405-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="0d405-117">Recommended action</span></span>

- <span data-ttu-id="0d405-118">수정된 문자열 데이터를 호출자로 다시 마샬링해야 하는 경우에는 대신 참조로 문자열을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-118">If you need to marshal modified string data back to the caller, pass the string by reference instead.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- <span data-ttu-id="0d405-119">수정된 문자열 데이터를 다시 호출자로 마샬링할 필요가 없는 경우에는 <xref:System.Runtime.InteropServices.OutAttribute>를 제거하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-119">If you don't need to marshal modified string data back to the caller, simply remove the <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  <span data-ttu-id="0d405-120">자세한 내용은 [CA1417](/visualstudio/code-quality/ca1417)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d405-120">For more information, see [CA1417](/visualstudio/code-quality/ca1417).</span></span>

- <span data-ttu-id="0d405-121">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-121">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="0d405-122">자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d405-122">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0d405-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0d405-123">Affected APIs</span></span>

<span data-ttu-id="0d405-124">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d405-124">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
