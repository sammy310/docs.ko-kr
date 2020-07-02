---
ms.openlocfilehash: 1d2e4a058008676c6ea85becebd4bb9220569ef3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621362"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a><span data-ttu-id="24443-101">텍스트 지원 컨트롤의 WPF 맞춤법 검사는 Windows 10에서 OS의 입력된 언어 목록에 없는 언어에 대해서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24443-101">WPF spell checking in text-enabled controls will not work in Windows 10 for languages not in the OS's input language list</span></span>

#### <a name="details"></a><span data-ttu-id="24443-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="24443-102">Details</span></span>

<span data-ttu-id="24443-103">Windows 10에서 실행하는 경우 플랫폼 맞춤법 검사 기능은 입력된 언어 목록에 있는 언어에 대해서만 사용할 수 있으므로 맞춤법 검사기가 WPF 텍스트 지원 컨트롤에서 작동하지 않을 수 있습니다. Windows 10에서 사용 가능한 키보드 목록에 언어가 추가되면 Windows는 맞춤법 검사 기능을 제공하는 해당 FOD(Feature on Demand) 패키지를 자동으로 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="24443-103">When running on Windows 10, the spell checker may not work for WPF text-enabled controls because platform spell-checking capabilities are available only for languages present in the input languages list.In Windows 10, when a language is added to the list of available keyboards, Windows automatically downloads and installs a corresponding Feature on Demand (FOD) package that provides spell-checking capabilities.</span></span> <span data-ttu-id="24443-104">입력 언어 목록에 언어를 추가하면 맞춤법 검사기가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="24443-104">By adding the language to the input languages list, the spell checker will be supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="24443-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="24443-105">Suggestion</span></span>

<span data-ttu-id="24443-106">Windows 10에서 맞춤법 검사가 작동하려면 맞춤법을 검사할 언어 또는 텍스트를 입력 언어로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24443-106">Be aware that the language or text to be spell-checked must be added as an input language for spell-checking to work in Windows 10.</span></span>

| <span data-ttu-id="24443-107">이름</span><span class="sxs-lookup"><span data-stu-id="24443-107">Name</span></span>    | <span data-ttu-id="24443-108">값</span><span class="sxs-lookup"><span data-stu-id="24443-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="24443-109">Scope</span><span class="sxs-lookup"><span data-stu-id="24443-109">Scope</span></span>   |<span data-ttu-id="24443-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="24443-110">Edge</span></span>|
|<span data-ttu-id="24443-111">버전</span><span class="sxs-lookup"><span data-stu-id="24443-111">Version</span></span>|<span data-ttu-id="24443-112">4.6</span><span class="sxs-lookup"><span data-stu-id="24443-112">4.6</span></span>|
|<span data-ttu-id="24443-113">형식</span><span class="sxs-lookup"><span data-stu-id="24443-113">Type</span></span>|<span data-ttu-id="24443-114">런타임</span><span class="sxs-lookup"><span data-stu-id="24443-114">Runtime</span></span>|
