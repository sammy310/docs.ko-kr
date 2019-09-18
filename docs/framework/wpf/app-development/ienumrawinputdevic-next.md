---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053407"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="d0064-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="d0064-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="d0064-103">열거자 목록에서 `celt` 다음 [rawinputdevice](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 구조를 열거 하 고의 실제 열거 된 `rgelt` 요소 `pceltFetched`수와 함께에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0064-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0064-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0064-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0064-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0064-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="d0064-106">진행 에서`rgelt`반환 된 [rawinputdevice](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 구조체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d0064-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="d0064-107">[out] 열거된 RAWINPUTDEVICE 구조체를 수신할 celt 크기(또는 더 큰)의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d0064-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="d0064-108">[out] `rgelt`에 실제로 제공된 요소 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0064-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="d0064-109">`NULL`가 1이면 호출자가 `rgelt`을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0064-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d0064-110">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="d0064-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="d0064-111">HRESULT: 제공 된 요소의 수가 이면 S_OK이 `celt`고, 그렇지 않으면입니다. 그렇지 않으면 S_FALSE입니다.</span><span class="sxs-lookup"><span data-stu-id="d0064-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
