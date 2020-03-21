---
title: IMetaDataEmit2::SaveDeltaToMemory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: 5ec4fe2a8e949cf6e9aa0ce68f4d4e49b72170b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177431"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="a0769-102">IMetaDataEmit2::SaveDeltaToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="a0769-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="a0769-103">현재 편집 및 계속 세션의 변경 내용을 메모리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a0769-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0769-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0769-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0769-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a0769-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="a0769-106">【아웃】 메타데이터 델타 작성을 시작할 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a0769-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="a0769-107">【인】 변경 사항의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a0769-107">[in] The size of the changes.</span></span> <span data-ttu-id="a0769-108">[IMetaDataEmit2를 사용:GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) 크기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0769-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0769-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0769-109">Requirements</span></span>  
 <span data-ttu-id="a0769-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0769-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0769-111">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="a0769-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0769-112">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a0769-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0769-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0769-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0769-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0769-114">See also</span></span>

- [<span data-ttu-id="a0769-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0769-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="a0769-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0769-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
