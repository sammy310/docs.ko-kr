---
title: IMetaDataEmit::GetSaveSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
ms.openlocfilehash: 125a63638a41707b8eed918253cb1f93abb907eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434329"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="d70c2-102">IMetaDataEmit::GetSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="d70c2-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="d70c2-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span><span class="sxs-lookup"><span data-stu-id="d70c2-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d70c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="d70c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d70c2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d70c2-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="d70c2-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span><span class="sxs-lookup"><span data-stu-id="d70c2-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="d70c2-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="d70c2-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="d70c2-108">cssAccurate returns the exact save size but takes longer to calculate.</span><span class="sxs-lookup"><span data-stu-id="d70c2-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="d70c2-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span><span class="sxs-lookup"><span data-stu-id="d70c2-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="d70c2-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span><span class="sxs-lookup"><span data-stu-id="d70c2-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="d70c2-111">[out] A pointer to the size that is required to save the file.</span><span class="sxs-lookup"><span data-stu-id="d70c2-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d70c2-112">주의</span><span class="sxs-lookup"><span data-stu-id="d70c2-112">Remarks</span></span>  
 <span data-ttu-id="d70c2-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span><span class="sxs-lookup"><span data-stu-id="d70c2-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="d70c2-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span><span class="sxs-lookup"><span data-stu-id="d70c2-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="d70c2-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span><span class="sxs-lookup"><span data-stu-id="d70c2-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="d70c2-116">Otherwise, no optimizations are performed.</span><span class="sxs-lookup"><span data-stu-id="d70c2-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="d70c2-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span><span class="sxs-lookup"><span data-stu-id="d70c2-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="d70c2-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span><span class="sxs-lookup"><span data-stu-id="d70c2-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="d70c2-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span><span class="sxs-lookup"><span data-stu-id="d70c2-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="d70c2-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="d70c2-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="d70c2-121">In this pass, another round of token mapping occurs.</span><span class="sxs-lookup"><span data-stu-id="d70c2-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="d70c2-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span><span class="sxs-lookup"><span data-stu-id="d70c2-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d70c2-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d70c2-123">Requirements</span></span>  
 <span data-ttu-id="d70c2-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d70c2-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d70c2-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d70c2-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d70c2-126">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d70c2-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d70c2-127">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d70c2-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d70c2-128">참조</span><span class="sxs-lookup"><span data-stu-id="d70c2-128">See also</span></span>

- [<span data-ttu-id="d70c2-129">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d70c2-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d70c2-130">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d70c2-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
