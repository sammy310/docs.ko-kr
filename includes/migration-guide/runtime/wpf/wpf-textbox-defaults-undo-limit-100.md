---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620480"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="145db-101">WPF TextBox 기본값이 100개의 제한을 실행 취소</span><span class="sxs-lookup"><span data-stu-id="145db-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="145db-102">설명</span><span class="sxs-lookup"><span data-stu-id="145db-102">Details</span></span>

<span data-ttu-id="145db-103">.NET Framework 4.5에서는 WPF TextBox에 대한 실행 취소 제한 기본값은 100(.NET Framework 4.0에서 무제한이던 것과 반대)</span><span class="sxs-lookup"><span data-stu-id="145db-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="145db-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="145db-104">Suggestion</span></span>

<span data-ttu-id="145db-105">100개의 실행 취소 제한이 너무 낮으면 제한을 <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>로 명시적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="145db-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="145db-106">이름</span><span class="sxs-lookup"><span data-stu-id="145db-106">Name</span></span>    | <span data-ttu-id="145db-107">값</span><span class="sxs-lookup"><span data-stu-id="145db-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="145db-108">Scope</span><span class="sxs-lookup"><span data-stu-id="145db-108">Scope</span></span>   |<span data-ttu-id="145db-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="145db-109">Edge</span></span>|
|<span data-ttu-id="145db-110">버전</span><span class="sxs-lookup"><span data-stu-id="145db-110">Version</span></span>|<span data-ttu-id="145db-111">4.5</span><span class="sxs-lookup"><span data-stu-id="145db-111">4.5</span></span>|
|<span data-ttu-id="145db-112">형식</span><span class="sxs-lookup"><span data-stu-id="145db-112">Type</span></span>|<span data-ttu-id="145db-113">런타임</span><span class="sxs-lookup"><span data-stu-id="145db-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="145db-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="145db-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
