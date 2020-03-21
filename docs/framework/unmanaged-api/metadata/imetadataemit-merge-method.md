---
title: IMetaDataEmit::병합 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: 759358822ed865c89f6f55084d1e7f6143506e93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175709"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="94cd1-102">IMetaDataEmit::병합 메서드</span><span class="sxs-lookup"><span data-stu-id="94cd1-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="94cd1-103">병합할 범위 목록에 지정된 가져온 범위를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="94cd1-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94cd1-104">구문</span><span class="sxs-lookup"><span data-stu-id="94cd1-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94cd1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94cd1-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="94cd1-106">【인】 병합할 가져온 범위를 식별하는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 개체에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="94cd1-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="94cd1-107">【인】 토큰 다시 매핑을 지정하는 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) 개체에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="94cd1-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="94cd1-108">【인】 오류를 지정하는 [IUnknown](/cpp/atl/iunknown) 개체에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="94cd1-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94cd1-109">설명</span><span class="sxs-lookup"><span data-stu-id="94cd1-109">Remarks</span></span>  
 <span data-ttu-id="94cd1-110">[IMetaDataEmit::MergeEnd호출하여](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) 메타데이터를 단일 범위로 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="94cd1-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94cd1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94cd1-111">Requirements</span></span>  
 <span data-ttu-id="94cd1-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94cd1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94cd1-113">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="94cd1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94cd1-114">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="94cd1-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94cd1-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94cd1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94cd1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94cd1-116">See also</span></span>

- [<span data-ttu-id="94cd1-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94cd1-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="94cd1-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94cd1-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
