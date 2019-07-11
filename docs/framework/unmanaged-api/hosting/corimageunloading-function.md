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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b488b6a887b0c66d8c17f8ea78f48f7d2ea31011
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758400"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="b6b30-102">_CorImageUnloading 함수</span><span class="sxs-lookup"><span data-stu-id="b6b30-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="b6b30-103">관리 되는 모듈 이미지가 언로드될 때 로더에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b6b30-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="b6b30-104">이 함수는 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b30-104">This function is not implemented.</span></span> <span data-ttu-id="b6b30-105">를 호출 하는 경우 E_NOTIMPL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b30-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6b30-106">구문</span><span class="sxs-lookup"><span data-stu-id="b6b30-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6b30-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6b30-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="b6b30-108">[in] 언로드할 이미지의 시작 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b30-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6b30-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6b30-109">Requirements</span></span>  
 <span data-ttu-id="b6b30-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6b30-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6b30-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b6b30-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6b30-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b6b30-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6b30-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6b30-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b30-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6b30-114">See also</span></span>

- [<span data-ttu-id="b6b30-115">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="b6b30-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
