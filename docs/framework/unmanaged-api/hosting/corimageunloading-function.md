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
ms.openlocfilehash: 4932e1fd6294f4a01264e982835dd0707324082a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178224"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="bd5d8-102">_CorImageUnloading 함수</span><span class="sxs-lookup"><span data-stu-id="bd5d8-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="bd5d8-103">관리되는 모듈 이미지가 언로드될 때 로더에 대해 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd5d8-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="bd5d8-104">이 함수는 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd5d8-104">This function is not implemented.</span></span> <span data-ttu-id="bd5d8-105">호출된 경우 E_NOTIMPL 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd5d8-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd5d8-106">구문</span><span class="sxs-lookup"><span data-stu-id="bd5d8-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd5d8-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd5d8-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="bd5d8-108">【인】 언로드할 이미지의 시작 위치에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd5d8-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd5d8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd5d8-109">Requirements</span></span>  
 <span data-ttu-id="bd5d8-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd5d8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd5d8-111">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="bd5d8-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd5d8-112">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="bd5d8-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd5d8-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd5d8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5d8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd5d8-114">See also</span></span>

- [<span data-ttu-id="bd5d8-115">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="bd5d8-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
