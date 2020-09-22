---
ms.openlocfilehash: 5529b8379c5cb9f1bc525e0c2340f6b885e35822
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606898"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a><span data-ttu-id="be943-101">중첩된 ToolStripMenuItems의 경우 ContextMenuStrip.SourceControl 속성은 유효한 컨트롤 포함함</span><span class="sxs-lookup"><span data-stu-id="be943-101">ContextMenuStrip.SourceControl property contains a valid control in the case of nested ToolStripMenuItems</span></span>

#### <a name="details"></a><span data-ttu-id="be943-102">설명</span><span class="sxs-lookup"><span data-stu-id="be943-102">Details</span></span>

<span data-ttu-id="be943-103">.NET Framework 4.7.1 및 이전 버전에서 사용자가 중첩된 <xref:System.Windows.Forms.ToolStripMenuItem> 컨트롤에서 메뉴를 열 경우 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> 속성은 null을 잘못 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="be943-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property incorrectly returns null when the user opens the menu from nested <xref:System.Windows.Forms.ToolStripMenuItem> controls.</span></span> <span data-ttu-id="be943-104">.NET framework 4.7.2 이상에서 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> 속성은 항상 실제 원본 제어로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="be943-104">In the .NET Framework 4.7.2 and later, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> property is always set to the actual source control.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="be943-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="be943-105">Suggestion</span></span>

<span data-ttu-id="be943-106">**이러한 변경을 옵트인 또는 옵트아웃하는 방법**: 애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.7.2 이상에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be943-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="be943-107">애플리케이션은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be943-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="be943-108">.NET Framework 4.7.2를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="be943-108">It targets the .NET Framework 4.7.2.</span></span> <span data-ttu-id="be943-109">이러한 변경 내용은 .NET Framework 4.7.2 이상을 대상으로 하는 Windows Forms 애플리케이션에서 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="be943-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="be943-110">.NET Framework 4.7.1 이전 버전을 대상으로 하며 다음 예제와 같이 app.config 파일의 `<runtime>` 섹션에 [AppContext 스위치](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 추가하고 이를 `false`로 설정하여 레거시 접근성 동작을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="be943-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

<span data-ttu-id="be943-111">.NET Framework 4.7.2 이상을 대상으로 하고 레거시 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 레거시 원본 제어 값 사용을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be943-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to the use of the legacy source control value by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="be943-112">이름</span><span class="sxs-lookup"><span data-stu-id="be943-112">Name</span></span>    | <span data-ttu-id="be943-113">값</span><span class="sxs-lookup"><span data-stu-id="be943-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="be943-114">Scope</span><span class="sxs-lookup"><span data-stu-id="be943-114">Scope</span></span>   | <span data-ttu-id="be943-115">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="be943-115">Edge</span></span>        |
| <span data-ttu-id="be943-116">버전</span><span class="sxs-lookup"><span data-stu-id="be943-116">Version</span></span> | <span data-ttu-id="be943-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="be943-117">4.7.2</span></span>       |
| <span data-ttu-id="be943-118">형식</span><span class="sxs-lookup"><span data-stu-id="be943-118">Type</span></span>    | <span data-ttu-id="be943-119">대상 변경</span><span class="sxs-lookup"><span data-stu-id="be943-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="be943-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="be943-120">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
