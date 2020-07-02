---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614795"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a><span data-ttu-id="a2831-101">휴대용 PDB를 사용할 때 가져온 스택 추적은 이제 요청된 경우 원본 파일 및 줄 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a2831-101">Stack traces obtained when using portable PDBs now include source file and line information if requested</span></span>

#### <a name="details"></a><span data-ttu-id="a2831-102">설명</span><span class="sxs-lookup"><span data-stu-id="a2831-102">Details</span></span>

<span data-ttu-id="a2831-103">.NET Framework 4.7.2부터 휴대용 PDB를 사용할 때 가져온 스택 추적은 요청된 경우 원본 파일 및 줄 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a2831-103">Starting with .NET Framework 4.7.2, stack traces obtained when using portable PDBs include source file and line information when requested.</span></span> <span data-ttu-id="a2831-104">.NET Framework 4.7.2 이전 버전에서 명시적으로 요청된 경우에도 휴대용 PDB를 사용할 때 원본 파일 및 줄 정보를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2831-104">In versions prior to .NET Framework 4.7.2, source file and line information would be unavailable when using portable PDBs even if explicitly requested.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a2831-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a2831-105">Suggestion</span></span>

<span data-ttu-id="a2831-106">.NET Framework 4.7.2를 대상으로 하는 애플리케이션의 경우, 필요하지 않으면 `app.config` 파일의 `<runtime>` 섹션에 다음을 추가하여 휴대용 PDB를 사용할 때 원본 파일 및 줄 정보를 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2831-106">For applications that target the .NET Framework 4.7.2, you can opt out of the source file and line information when using portable PDBs if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

<span data-ttu-id="a2831-107">이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.2 이상에서 실행되는 애플리케이션의 경우 `app.config` 파일의 `<runtime>` 섹션에 다음을 추가하여 휴대용 PDB를 사용할 때 원본 파일 및 줄 정보를 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2831-107">For applications that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.2 or later, you can opt in to the source file and line information when using portable PDBs by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| <span data-ttu-id="a2831-108">이름</span><span class="sxs-lookup"><span data-stu-id="a2831-108">Name</span></span>    | <span data-ttu-id="a2831-109">값</span><span class="sxs-lookup"><span data-stu-id="a2831-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a2831-110">Scope</span><span class="sxs-lookup"><span data-stu-id="a2831-110">Scope</span></span>   | <span data-ttu-id="a2831-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a2831-111">Edge</span></span>        |
| <span data-ttu-id="a2831-112">버전</span><span class="sxs-lookup"><span data-stu-id="a2831-112">Version</span></span> | <span data-ttu-id="a2831-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="a2831-113">4.7.2</span></span>       |
| <span data-ttu-id="a2831-114">형식</span><span class="sxs-lookup"><span data-stu-id="a2831-114">Type</span></span>    | <span data-ttu-id="a2831-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="a2831-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a2831-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a2831-116">Affected APIs</span></span>

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
