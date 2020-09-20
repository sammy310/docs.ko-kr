---
ms.openlocfilehash: ada458ffeeba95d4989507f90c789b159f359797
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065169"
---
### <a name="ca1417-outattribute-on-string-parameter-for-pinvoke"></a><span data-ttu-id="998bf-101">CA1417: P/Invoke에 대한 문자열 매개 변수의 OutAttribute</span><span class="sxs-lookup"><span data-stu-id="998bf-101">CA1417: OutAttribute on string parameter for P/Invoke</span></span>

<span data-ttu-id="998bf-102">.NET 코드 분석기 규칙 [CA1417](/visualstudio/code-quality/ca1417)은 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-102">.NET code analyzer rule [CA1417](/visualstudio/code-quality/ca1417) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="998bf-103"><xref:System.String> 매개 변수가 값으로 전달되고 <xref:System.Runtime.InteropServices.OutAttribute>로 표시된 [P/Invoke(플랫폼 호출)](../../../../docs/standard/native-interop/pinvoke.md) 메서드 정의에 대해 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-103">It produces a build warning for any [Platform Invoke (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is passed by value and marked with <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="998bf-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="998bf-104">Change description</span></span>

<span data-ttu-id="998bf-105">.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../docs/fundamentals/productivity/code-analysis.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="998bf-106">[CA1417](/visualstudio/code-quality/ca1417)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-106">Several of these rules are enabled, by default, including [CA1417](/visualstudio/code-quality/ca1417).</span></span> <span data-ttu-id="998bf-107">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="998bf-108">규칙 CA1417은 <xref:System.String> 매개 변수가 <xref:System.Runtime.InteropServices.OutAttribute> 특성으로 표시되고 값으로 전달된 [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) 메서드 정의를 플래그로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-108">Rule CA1417 flags [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is marked with the <xref:System.Runtime.InteropServices.OutAttribute> attribute and is passed by value.</span></span> <span data-ttu-id="998bf-109">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="998bf-109">For example:</span></span>

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

<span data-ttu-id="998bf-110">.NET 런타임은 특정 프로그램에서 고유한 각 리터럴 문자열에 대한 단일 참조를 포함하는 인턴 풀이라는 테이블을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-110">The .NET runtime maintains a table, called the intern pool, that contains a single reference to each unique literal string in a program.</span></span> <span data-ttu-id="998bf-111"><xref:System.Runtime.InteropServices.OutAttribute>로 표시된 인터닝된 문자열이 P/Invoke 메서드에 숫자로 전달되는 경우 런타임은 불안정해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-111">If an interned string marked with <xref:System.Runtime.InteropServices.OutAttribute> is passed by value to a P/Invoke method, the runtime can be destabilized.</span></span> <span data-ttu-id="998bf-112">문자열 인터닝에 대한 자세한 내용은 <xref:System.String.Intern(System.String)?displayProperty=nameWithType>에 대한 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="998bf-112">For more information about string interning, see the remarks for <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="998bf-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="998bf-113">Version introduced</span></span>

<span data-ttu-id="998bf-114">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="998bf-114">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="998bf-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="998bf-115">Recommended action</span></span>

- <span data-ttu-id="998bf-116">수정된 문자열 데이터를 호출자로 다시 마샬링해야 하는 경우에는 대신 참조로 문자열을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-116">If you need to marshal modified string data back to the caller, pass the string by reference instead.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- <span data-ttu-id="998bf-117">수정된 문자열 데이터를 다시 호출자로 마샬링할 필요가 없는 경우에는 <xref:System.Runtime.InteropServices.OutAttribute>를 제거하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-117">If you don't need to marshal modified string data back to the caller, simply remove the <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  <span data-ttu-id="998bf-118">자세한 내용은 [CA1417](/visualstudio/code-quality/ca1417)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="998bf-118">For more information, see [CA1417](/visualstudio/code-quality/ca1417).</span></span>

- <span data-ttu-id="998bf-119">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-119">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="998bf-120">자세한 내용은 [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="998bf-120">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="998bf-121">범주</span><span class="sxs-lookup"><span data-stu-id="998bf-121">Category</span></span>

<span data-ttu-id="998bf-122">코드 분석</span><span class="sxs-lookup"><span data-stu-id="998bf-122">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="998bf-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="998bf-123">Affected APIs</span></span>

<span data-ttu-id="998bf-124">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="998bf-124">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
