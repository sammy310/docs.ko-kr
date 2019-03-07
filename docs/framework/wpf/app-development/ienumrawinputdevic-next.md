---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 05867af48b64cd1898b13fa055859c8cc0367c8c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494183"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="7a6eb-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="7a6eb-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="7a6eb-103">다음 열거 `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 구조에 반환 되는 열거자의 목록에서 `rgelt` 실제 열거 된 요소 수와 함께 `pceltFetched`입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6eb-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a6eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="7a6eb-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a6eb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7a6eb-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="7a6eb-106">[in] 수가 [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 에서 반환 된 `rgelt`합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6eb-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="7a6eb-107">[out] 열거된 RAWINPUTDEVICE 구조체를 수신할 celt 크기(또는 더 큰)의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6eb-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="7a6eb-108">[out] `rgelt`에 실제로 제공된 요소 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6eb-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="7a6eb-109">`rgelt`가 1이면 호출자가 `NULL`을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6eb-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7a6eb-110">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="7a6eb-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="7a6eb-111">HRESULT: 제공 된 요소 수가 S_OK `celt`; 그렇지 않으면 S_FALSE입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6eb-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
