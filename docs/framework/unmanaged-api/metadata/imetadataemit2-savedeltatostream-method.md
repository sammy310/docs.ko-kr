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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dcb94323c9950b8e1fe56ca3dae5f41a9c801907
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472124"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="0da40-102">IMetaDataEmit2::SaveDeltaToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="0da40-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="0da40-103">편집 하며 계속 하기는 현재 세션에서 지정 된 스트림에 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0da40-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da40-104">구문</span><span class="sxs-lookup"><span data-stu-id="0da40-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da40-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0da40-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="0da40-106">[in] 변경 내용을 저장 하는 쓰기 가능한 스트림에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0da40-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="0da40-107">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0da40-107">[in] Reserved.</span></span> <span data-ttu-id="0da40-108">이 값은 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0da40-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da40-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0da40-109">Requirements</span></span>  
 <span data-ttu-id="0da40-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0da40-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0da40-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0da40-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0da40-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0da40-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0da40-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0da40-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da40-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="0da40-114">See also</span></span>
- [<span data-ttu-id="0da40-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0da40-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="0da40-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0da40-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
