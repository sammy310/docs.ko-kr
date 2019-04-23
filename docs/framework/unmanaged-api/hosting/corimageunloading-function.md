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
ms.openlocfilehash: 1cb5f9decbcdfb71f67a5132dc59773f1de8b0a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086431"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="fd207-102">_CorImageUnloading 함수</span><span class="sxs-lookup"><span data-stu-id="fd207-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="fd207-103">관리 되는 모듈 이미지가 언로드될 때 로더에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fd207-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="fd207-104">이 함수는 구현 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="fd207-104">This function is not implemented.</span></span> <span data-ttu-id="fd207-105">를 호출 하는 경우 E_NOTIMPL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd207-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd207-106">구문</span><span class="sxs-lookup"><span data-stu-id="fd207-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd207-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd207-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="fd207-108">[in] 언로드할 이미지의 시작 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd207-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd207-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd207-109">Requirements</span></span>  
 <span data-ttu-id="fd207-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd207-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd207-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fd207-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd207-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fd207-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd207-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd207-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd207-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="fd207-114">See also</span></span>

- [<span data-ttu-id="fd207-115">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="fd207-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
