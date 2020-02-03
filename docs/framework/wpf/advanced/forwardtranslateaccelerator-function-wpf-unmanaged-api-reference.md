---
title: ForwardTranslateAccelerator 함수-WPF 관리 되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747043"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="f1def-102">ForwardTranslateAccelerator 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="f1def-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="f1def-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f1def-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="f1def-104">Windows 관리를 위한 WPF (Windows Presentation Foundation) 인프라에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1def-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1def-105">구문</span><span class="sxs-lookup"><span data-stu-id="f1def-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1def-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1def-106">Parameters</span></span>  
 <span data-ttu-id="f1def-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="f1def-107">pMsg</span></span>  
 <span data-ttu-id="f1def-108">메시지에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1def-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="f1def-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="f1def-109">appUnhandled</span></span>  
 <span data-ttu-id="f1def-110">앱이 이미 입력 메시지를 처리할 수 있는 기회를 제공 했지만 처리 하지 않은 경우를 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f1def-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1def-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1def-111">Requirements</span></span>  
 <span data-ttu-id="f1def-112">**플랫폼:** [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f1def-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1def-113">**GDIPLUS.DLL**</span><span class="sxs-lookup"><span data-stu-id="f1def-113">**DLL:**</span></span>  
  
 <span data-ttu-id="f1def-114">.NET Framework 3.0 및 3.5: PresentationHostDLL에서</span><span class="sxs-lookup"><span data-stu-id="f1def-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="f1def-115">.NET Framework 4 이상: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="f1def-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="f1def-116">**.NET Framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1def-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1def-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1def-117">See also</span></span>

- [<span data-ttu-id="f1def-118">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="f1def-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
