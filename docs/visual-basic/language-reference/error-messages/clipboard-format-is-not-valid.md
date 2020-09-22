---
title: 클립보드 형식이 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 429d1e120a0044152a358a87663eb09989f45b0e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874585"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="cd227-102">클립보드 형식이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd227-102">Clipboard format is not valid</span></span>

<span data-ttu-id="cd227-103">지정 된 클립보드 형식이 실행 중인 메서드와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd227-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="cd227-104">이 오류는 다음과 같은 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd227-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="cd227-105">`GetText` `SetText` 또는 이외의 클립보드 형식으로 클립보드의 또는 메서드를 사용 하 `vbCFText` 는 `vbCFLink` 경우</span><span class="sxs-lookup"><span data-stu-id="cd227-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
- <span data-ttu-id="cd227-106">클립보드의 `GetData` 또는 `SetData` 메서드 `vbCFBitmap` 를, 또는 이외의 클립보드 형식으로 사용 `vbCFDIB` 하 `vbCFMetafile` 는 경우</span><span class="sxs-lookup"><span data-stu-id="cd227-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
- <span data-ttu-id="cd227-107">등록 된 `GetData` `SetData` `DataObject` 형식 (&HC000-&hffff)에 대해 microsoft windows에서 예약한 범위에서 클립보드 형식의 또는 메서드를 사용 하 여 microsoft windows에 등록 하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="cd227-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cd227-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="cd227-108">To correct this error</span></span>  
  
- <span data-ttu-id="cd227-109">잘못 된 형식을 제거 하 고 올바른 형식을 지정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd227-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd227-110">참조</span><span class="sxs-lookup"><span data-stu-id="cd227-110">See also</span></span>

- [<span data-ttu-id="cd227-111">클립보드: 다른 형식 추가</span><span class="sxs-lookup"><span data-stu-id="cd227-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
