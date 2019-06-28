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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65dbfd526110be5b9b3348fb677fbde7301e4038
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424654"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="38283-102">IMetaDataEmit::병합 메서드</span><span class="sxs-lookup"><span data-stu-id="38283-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="38283-103">병합할 범위의 목록에 지정된 된 가져온된 범위를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="38283-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38283-104">구문</span><span class="sxs-lookup"><span data-stu-id="38283-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38283-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38283-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="38283-106">[in] 에 대 한 포인터를 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 병합할 가져온된 범위를 식별 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="38283-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="38283-107">[in] 에 대 한 포인터를 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) 토큰 다시 매핑을 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="38283-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="38283-108">[in] 에 대 한 포인터를 [IUnknown](/cpp/atl/iunknown) 오류를 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="38283-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38283-109">설명</span><span class="sxs-lookup"><span data-stu-id="38283-109">Remarks</span></span>  
 <span data-ttu-id="38283-110">호출 [imetadataemit:: Mergeend](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) 단일 범위로 메타 데이터는 병합을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38283-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38283-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38283-111">Requirements</span></span>  
 <span data-ttu-id="38283-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="38283-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38283-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="38283-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38283-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="38283-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38283-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38283-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38283-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="38283-116">See also</span></span>

- [<span data-ttu-id="38283-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38283-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="38283-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38283-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
