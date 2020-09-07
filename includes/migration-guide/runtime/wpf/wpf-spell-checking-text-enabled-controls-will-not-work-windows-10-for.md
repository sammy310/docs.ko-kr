---
ms.openlocfilehash: 6d7f998cda6326e1f584713576a0aa27b3a68655
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497018"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a><span data-ttu-id="afbe6-101">텍스트 지원 컨트롤의 WPF 맞춤법 검사는 Windows 10에서 OS의 입력된 언어 목록에 없는 언어에 대해서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="afbe6-101">WPF spell checking in text-enabled controls will not work in Windows 10 for languages not in the OS's input language list</span></span>

#### <a name="details"></a><span data-ttu-id="afbe6-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="afbe6-102">Details</span></span>

<span data-ttu-id="afbe6-103">Windows 10에서 실행하는 경우 플랫폼 맞춤법 검사 기능은 입력된 언어 목록에 있는 언어에 대해서만 사용할 수 있으므로 맞춤법 검사기가 WPF 텍스트 지원 컨트롤에서 작동하지 않을 수 있습니다. Windows 10에서 사용 가능한 키보드 목록에 언어가 추가되면 Windows는 맞춤법 검사 기능을 제공하는 해당 FOD(Feature on Demand) 패키지를 자동으로 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="afbe6-103">When running on Windows 10, the spell checker may not work for WPF text-enabled controls because platform spell-checking capabilities are available only for languages present in the input languages list.In Windows 10, when a language is added to the list of available keyboards, Windows automatically downloads and installs a corresponding Feature on Demand (FOD) package that provides spell-checking capabilities.</span></span> <span data-ttu-id="afbe6-104">입력 언어 목록에 언어를 추가하면 맞춤법 검사기가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="afbe6-104">By adding the language to the input languages list, the spell checker will be supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="afbe6-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="afbe6-105">Suggestion</span></span>

<span data-ttu-id="afbe6-106">Windows 10에서 맞춤법 검사가 작동하려면 맞춤법을 검사할 언어 또는 텍스트를 입력 언어로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afbe6-106">Be aware that the language or text to be spell-checked must be added as an input language for spell-checking to work in Windows 10.</span></span>

| <span data-ttu-id="afbe6-107">Name</span><span class="sxs-lookup"><span data-stu-id="afbe6-107">Name</span></span>    | <span data-ttu-id="afbe6-108">값</span><span class="sxs-lookup"><span data-stu-id="afbe6-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="afbe6-109">Scope</span><span class="sxs-lookup"><span data-stu-id="afbe6-109">Scope</span></span>   |<span data-ttu-id="afbe6-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="afbe6-110">Edge</span></span>|
|<span data-ttu-id="afbe6-111">버전</span><span class="sxs-lookup"><span data-stu-id="afbe6-111">Version</span></span>|<span data-ttu-id="afbe6-112">4.6</span><span class="sxs-lookup"><span data-stu-id="afbe6-112">4.6</span></span>|
|<span data-ttu-id="afbe6-113">형식</span><span class="sxs-lookup"><span data-stu-id="afbe6-113">Type</span></span>|<span data-ttu-id="afbe6-114">런타임</span><span class="sxs-lookup"><span data-stu-id="afbe6-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="afbe6-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="afbe6-115">Affected APIs</span></span>

<span data-ttu-id="afbe6-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="afbe6-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
