---
description: _CorImageUnloading 함수에 대해 자세히 알아보세요.
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
ms.openlocfilehash: fe10c97be66aab21793b1ad306aa5d90eaa1ade2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716993"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="6a008-103">_CorImageUnloading 함수</span><span class="sxs-lookup"><span data-stu-id="6a008-103">_CorImageUnloading Function</span></span>

<span data-ttu-id="6a008-104">관리 되는 모듈 이미지가 언로드될 때 로더에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6a008-104">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="6a008-105">이 함수는 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a008-105">This function is not implemented.</span></span> <span data-ttu-id="6a008-106">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a008-106">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a008-107">구문</span><span class="sxs-lookup"><span data-stu-id="6a008-107">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a008-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a008-108">Parameters</span></span>  

 `ImageBase`  
 <span data-ttu-id="6a008-109">진행 언로드할 이미지의 시작 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6a008-109">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a008-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a008-110">Requirements</span></span>  

 <span data-ttu-id="6a008-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a008-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a008-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6a008-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a008-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a008-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6a008-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a008-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a008-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a008-115">See also</span></span>

- [<span data-ttu-id="6a008-116">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="6a008-116">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
