---
ms.openlocfilehash: f78d15338aa49de5b729aca12964924a0df00ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614834"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a><span data-ttu-id="32747-101">일부 .NET SDK 도구에 대해 향상된 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="32747-101">Improved accessibility for some .NET SDK tools</span></span>

#### <a name="details"></a><span data-ttu-id="32747-102">설명</span><span class="sxs-lookup"><span data-stu-id="32747-102">Details</span></span>

<span data-ttu-id="32747-103">.NET Framework SDK 4.7.1에서 다양한 액세스 가능성 문제를 수정하여 SvcConfigEditor.exe 및 SvcTraceViewer.exe 도구가 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32747-103">In the .NET Framework SDK 4.7.1, the SvcConfigEditor.exe and SvcTraceViewer.exe tools have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="32747-104">이들 중 대부분은 정의되지 않은 이름이나 특정 UI 자동화 패턴이 올바르게 구현되지 않은 것과 같은 사소한 문제였습니다.</span><span class="sxs-lookup"><span data-stu-id="32747-104">Most of these were small issues like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="32747-105">많은 사용자가 이러한 잘못된 값을 인식하지 못하지만, 화면 판독기와 같은 보조 기술을 사용하는 고객은 이러한 SDK 도구를 보다 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32747-105">While many users wouldn't be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> <span data-ttu-id="32747-106">물론 이러한 수정은 키보드 포커스 순서와 같은 이전 동작을 변경합니다. 이 도구에서 모든 액세스 가능성을 수정하기 위해 app.config 파일에서 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32747-106">Certainly, these fixes change some previous behaviors, like keyboard focus order.In order to get all the accessibility fixes in these tools, you can the following to your app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false"/>
</runtime>
```

| <span data-ttu-id="32747-107">이름</span><span class="sxs-lookup"><span data-stu-id="32747-107">Name</span></span>    | <span data-ttu-id="32747-108">값</span><span class="sxs-lookup"><span data-stu-id="32747-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="32747-109">Scope</span><span class="sxs-lookup"><span data-stu-id="32747-109">Scope</span></span>   | <span data-ttu-id="32747-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="32747-110">Edge</span></span>        |
| <span data-ttu-id="32747-111">버전</span><span class="sxs-lookup"><span data-stu-id="32747-111">Version</span></span> | <span data-ttu-id="32747-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="32747-112">4.7.1</span></span>       |
| <span data-ttu-id="32747-113">형식</span><span class="sxs-lookup"><span data-stu-id="32747-113">Type</span></span>    | <span data-ttu-id="32747-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="32747-114">Retargeting</span></span> |
