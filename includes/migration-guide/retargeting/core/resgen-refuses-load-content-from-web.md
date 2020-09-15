---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614770"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a><span data-ttu-id="d10d2-101">Resgen에서 웹으로부터 콘텐츠 로드를 거부</span><span class="sxs-lookup"><span data-stu-id="d10d2-101">Resgen refuses to load content from the web</span></span>

#### <a name="details"></a><span data-ttu-id="d10d2-102">설명</span><span class="sxs-lookup"><span data-stu-id="d10d2-102">Details</span></span>

<span data-ttu-id="d10d2-103">.resx 파일에는 이진 형식의 입력이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d10d2-103">.resx files may contain binary formatted input.</span></span> <span data-ttu-id="d10d2-104">Resgen을 사용하여 신뢰할 수 없는 위치에서 다운로드한 파일을 로드하려고 하면 기본적으로 입력이 로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d10d2-104">If you attempt to use resgen to load a file that was downloaded from an untrusted location, it will fail to load the input by default.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d10d2-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d10d2-105">Suggestion</span></span>

<span data-ttu-id="d10d2-106">신뢰할 수 없는 위치에서 이진 형식 입력을 로드해야 하는 Resgen 사용자는 입력 파일에서 웹 표시를 제거하거나 쿼크 옵트아웃을 적용할 수 있습니다. 컴퓨터 수준에서 쿼크 옵트아웃을 적용하려면 다음 레지스트리 설정을 추가합니다. [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span><span class="sxs-lookup"><span data-stu-id="d10d2-106">Resgen users who require loading binary formatted input from untrusted locations can either remove the mark of the web from the input file or apply the opt-out quirk.Add the following registry setting to apply the machine wide opt-out quirk: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span></span>

| <span data-ttu-id="d10d2-107">이름</span><span class="sxs-lookup"><span data-stu-id="d10d2-107">Name</span></span>    | <span data-ttu-id="d10d2-108">값</span><span class="sxs-lookup"><span data-stu-id="d10d2-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d10d2-109">Scope</span><span class="sxs-lookup"><span data-stu-id="d10d2-109">Scope</span></span>   | <span data-ttu-id="d10d2-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d10d2-110">Edge</span></span>        |
| <span data-ttu-id="d10d2-111">버전</span><span class="sxs-lookup"><span data-stu-id="d10d2-111">Version</span></span> | <span data-ttu-id="d10d2-112">4.7.2</span><span class="sxs-lookup"><span data-stu-id="d10d2-112">4.7.2</span></span>       |
| <span data-ttu-id="d10d2-113">형식</span><span class="sxs-lookup"><span data-stu-id="d10d2-113">Type</span></span>    | <span data-ttu-id="d10d2-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="d10d2-114">Retargeting</span></span> |
