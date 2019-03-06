---
title: ForwardTranslateAccelerator 함수 (F 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: 02d5d23ec44d9fb7a244fc635ac174cf81ead173
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362190"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="3355b-102">ForwardTranslateAccelerator 함수 (F 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="3355b-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="3355b-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3355b-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="3355b-104">Windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3355b-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3355b-105">구문</span><span class="sxs-lookup"><span data-stu-id="3355b-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3355b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3355b-106">Parameters</span></span>  
 <span data-ttu-id="3355b-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="3355b-107">pMsg</span></span>  
 <span data-ttu-id="3355b-108">메시지에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3355b-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="3355b-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="3355b-109">appUnhandled</span></span>  
 <span data-ttu-id="3355b-110">`true` 앱에 이미 지정 된 입력된 메시지를 처리할 수 있는 기회가 되지만, 처리 하지 경우 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="3355b-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3355b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3355b-111">Requirements</span></span>  
 <span data-ttu-id="3355b-112">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3355b-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3355b-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="3355b-113">**DLL:**</span></span>  
  
 <span data-ttu-id="3355b-114">.NET framework 3.0 및 3.5. PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="3355b-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="3355b-115">.NET framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="3355b-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="3355b-116">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3355b-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3355b-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="3355b-117">See also</span></span>
- [<span data-ttu-id="3355b-118">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="3355b-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
