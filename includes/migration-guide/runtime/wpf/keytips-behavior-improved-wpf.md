---
ms.openlocfilehash: 9659068304eb208fd6a0a753273453bc669fbc56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621273"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="42770-101">WPF의 향상된 키 팁 동작</span><span class="sxs-lookup"><span data-stu-id="42770-101">Keytips behavior improved in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="42770-102">설명</span><span class="sxs-lookup"><span data-stu-id="42770-102">Details</span></span>

<span data-ttu-id="42770-103">Microsoft Word 및 Windows Explorer에서 동작으로 패리티를 가져오기 위해 키 팁 동작이 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42770-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="42770-104">키 팁 상태가 사용하도록 설정되거나 <xref:System.Windows.Input.KeyEventArgs.SystemKey>(특히 <xref:System.Windows.Input.Key> 또는 <xref:System.Windows.Input.Key.F11>)이 눌러지지 않았는지 여부를 확인하여 WPF는 키 팁 키를 적절히 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="42770-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="42770-105">이제 키 팁은 마우스에 의해 열릴 경우에도 메뉴를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="42770-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="42770-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="42770-106">Suggestion</span></span>

<span data-ttu-id="42770-107">N/A</span><span class="sxs-lookup"><span data-stu-id="42770-107">N/A</span></span>

| <span data-ttu-id="42770-108">이름</span><span class="sxs-lookup"><span data-stu-id="42770-108">Name</span></span>    | <span data-ttu-id="42770-109">값</span><span class="sxs-lookup"><span data-stu-id="42770-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="42770-110">Scope</span><span class="sxs-lookup"><span data-stu-id="42770-110">Scope</span></span>   |<span data-ttu-id="42770-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="42770-111">Edge</span></span>|
|<span data-ttu-id="42770-112">버전</span><span class="sxs-lookup"><span data-stu-id="42770-112">Version</span></span>|<span data-ttu-id="42770-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="42770-113">4.7.2</span></span>|
|<span data-ttu-id="42770-114">형식</span><span class="sxs-lookup"><span data-stu-id="42770-114">Type</span></span>|<span data-ttu-id="42770-115">런타임</span><span class="sxs-lookup"><span data-stu-id="42770-115">Runtime</span></span>|
