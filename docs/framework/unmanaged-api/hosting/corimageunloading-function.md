---
title: _CorImageUnloading 함수
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
ms.openlocfilehash: 585287f63f57f55e877c94684820833b6d1add60
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616540"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="54ca2-102">_CorImageUnloading 함수</span><span class="sxs-lookup"><span data-stu-id="54ca2-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="54ca2-103">관리 되는 모듈 이미지가 언로드될 때 로더에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="54ca2-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="54ca2-104">이 함수는 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54ca2-104">This function is not implemented.</span></span> <span data-ttu-id="54ca2-105">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54ca2-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54ca2-106">구문</span><span class="sxs-lookup"><span data-stu-id="54ca2-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54ca2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="54ca2-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="54ca2-108">진행 언로드할 이미지의 시작 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="54ca2-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54ca2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54ca2-109">Requirements</span></span>  
 <span data-ttu-id="54ca2-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54ca2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54ca2-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="54ca2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="54ca2-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54ca2-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="54ca2-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54ca2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ca2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54ca2-114">See also</span></span>

- [<span data-ttu-id="54ca2-115">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="54ca2-115">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
