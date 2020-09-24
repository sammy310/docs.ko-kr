---
ms.openlocfilehash: 4bc8db52efdfe483acb4f6b6e33c4fa7716e0b79
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770961"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="ebd62-101">svcTraceViewer ComboBox 고대비 변경</span><span class="sxs-lookup"><span data-stu-id="ebd62-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="ebd62-102">설명</span><span class="sxs-lookup"><span data-stu-id="ebd62-102">Details</span></span>

<span data-ttu-id="ebd62-103">[Microsoft Service Trace Viewer 도구](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)에서 ComboBox 컨트롤이 특정 고대비 테마에서 올바른 색으로 표시되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd62-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="ebd62-104">이 문제는 .NET Framework 4.7.2에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd62-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="ebd62-105">그러나 .NET Framework SDK의 이전 버전과의 호환성 요구 사항으로 인해, 이 수정 사항은 기본적으로 고객에게 보이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd62-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="ebd62-106">.NET 4.8은 다음 [AppContext 구성 스위치](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 svcTraceViewer.exe.config 파일에 추가하여 이 변경 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd62-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

#### <a name="suggestion"></a><span data-ttu-id="ebd62-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="ebd62-107">Suggestion</span></span>

<span data-ttu-id="ebd62-108">고대비 동작을 변경하지 않으려는 경우 svcTraceViewer.exe.config 파일에서 다음 섹션을 제거하여 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd62-108">If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

| <span data-ttu-id="ebd62-109">이름</span><span class="sxs-lookup"><span data-stu-id="ebd62-109">Name</span></span>    | <span data-ttu-id="ebd62-110">값</span><span class="sxs-lookup"><span data-stu-id="ebd62-110">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="ebd62-111">Scope</span><span class="sxs-lookup"><span data-stu-id="ebd62-111">Scope</span></span>   | <span data-ttu-id="ebd62-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ebd62-112">Edge</span></span>    |
| <span data-ttu-id="ebd62-113">버전</span><span class="sxs-lookup"><span data-stu-id="ebd62-113">Version</span></span> | <span data-ttu-id="ebd62-114">4.8</span><span class="sxs-lookup"><span data-stu-id="ebd62-114">4.8</span></span>     |
| <span data-ttu-id="ebd62-115">형식</span><span class="sxs-lookup"><span data-stu-id="ebd62-115">Type</span></span>    | <span data-ttu-id="ebd62-116">런타임</span><span class="sxs-lookup"><span data-stu-id="ebd62-116">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="ebd62-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ebd62-117">Affected APIs</span></span>

<span data-ttu-id="ebd62-118">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd62-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
