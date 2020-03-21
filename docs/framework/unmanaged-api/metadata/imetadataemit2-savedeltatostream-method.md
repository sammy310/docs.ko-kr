---
title: IMetaDataEmit2::SaveDeltaToStream 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: 7e8376f3a029b0e3ec51a1e7587dd14b3e7530ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177421"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="cc72b-102">IMetaDataEmit2::SaveDeltaToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="cc72b-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="cc72b-103">현재 편집 및 계속 세션의 변경 내용을 지정된 스트림에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cc72b-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc72b-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc72b-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc72b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc72b-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="cc72b-106">【인】 변경 내용을 저장할 쓰기 가능한 스트림에 대한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cc72b-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="cc72b-107">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc72b-107">[in] Reserved.</span></span> <span data-ttu-id="cc72b-108">이 값은 0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc72b-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc72b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc72b-109">Requirements</span></span>  
 <span data-ttu-id="cc72b-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc72b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc72b-111">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="cc72b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc72b-112">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="cc72b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc72b-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc72b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc72b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc72b-114">See also</span></span>

- [<span data-ttu-id="cc72b-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc72b-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="cc72b-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc72b-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
