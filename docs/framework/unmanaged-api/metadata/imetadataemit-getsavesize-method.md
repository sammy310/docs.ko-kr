---
description: '자세히 알아보기: IMetaDataEmit:: GetSaveSize 메서드'
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
ms.openlocfilehash: 871e9f911eaaf1b1a7259466402e492d75aa7fb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783939"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="1e054-103">IMetaDataEmit::GetSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="1e054-103">IMetaDataEmit::GetSaveSize Method</span></span>

<span data-ttu-id="1e054-104">현재 범위에서 어셈블리의 예상 이진 크기와 해당 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-104">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e054-105">구문</span><span class="sxs-lookup"><span data-stu-id="1e054-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e054-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e054-106">Parameters</span></span>  

 `fSave`  
 <span data-ttu-id="1e054-107">진행 정확 하 게 또는 대략적인 크기를 가져올 것인지 여부를 지정 하는 [CorSaveSize](corsavesize-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-107">[in] A value of the [CorSaveSize](corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="1e054-108">CssAccurate, cssQuick 및 cssDiscardTransientCAs의 세 가지 값만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-108">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="1e054-109">cssAccurate는 정확한 저장 크기를 반환 하지만 계산 하는 데 더 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-109">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="1e054-110">cssQuick은 안전을 위해 채워진 크기를 반환 하지만 계산 하는 데 시간이 더 짧습니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-110">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="1e054-111">cssDiscardTransientCAs `GetSaveSize` 는 삭제 가능한 사용자 지정 특성을 throw 할 수 있음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-111">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="1e054-112">제한이 파일을 저장 하는 데 필요한 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-112">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e054-113">설명</span><span class="sxs-lookup"><span data-stu-id="1e054-113">Remarks</span></span>  

 <span data-ttu-id="1e054-114">`GetSaveSize` 현재 범위에서 어셈블리와 모든 메타 데이터를 저장 하는 데 필요한 공간 (바이트)을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-114">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="1e054-115">[IMetaDataEmit:: SaveToStream](imetadataemit-savetostream-method.md) 메서드를 호출 하면이 바이트 수가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-115">(A call to the [IMetaDataEmit::SaveToStream](imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="1e054-116">호출자가 [IMapToken](imaptoken-interface.md) 인터페이스를 구현 하는 경우 ( [IMetaDataEmit:: SetHandler](imetadataemit-sethandler-method.md) 또는 [IMetaDataEmit:: Merge](imetadataemit-merge-method.md))는 `GetSaveSize` 메타 데이터에 대해 두 개의 패스를 수행 하 여 최적화 하 고 압축 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-116">If the caller implements the [IMapToken](imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="1e054-117">그렇지 않으면 최적화가 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-117">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="1e054-118">최적화를 수행 하는 경우 첫 번째 패스는 단지 메타 데이터 구조를 정렬 하 여 가져오기 시간 검색의 성능을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-118">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="1e054-119">이 단계에서는 일반적으로 레코드를 이동 하 고 나중에 참조할 수 있도록 도구에 의해 유지 된 토큰의 부작용이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-119">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="1e054-120">그러나 메타 데이터는 두 번째 통과 이후까지 이러한 토큰 변경을 호출자에 게 알리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-120">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="1e054-121">두 번째 단계에서는 `mdTypeRef` `mdMemberRef` 현재 메타 데이터 범위에 선언 된 형식 또는 멤버에 대 한 참조가 있는 경우 (초기 바인딩) 및 토큰을 최적화 하는 것과 같이 메타 데이터의 전체 크기를 줄이기 위해 다양 한 최적화가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-121">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="1e054-122">이 패스에는 토큰 매핑의 또 다른 왕복이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-122">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="1e054-123">이 단계를 수행한 후 메타 데이터 엔진은 해당 `IMapToken` 인터페이스를 통해 변경 된 모든 토큰 값의 호출자에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-123">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e054-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e054-124">Requirements</span></span>  

 <span data-ttu-id="1e054-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e054-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e054-126">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1e054-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e054-127">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-127">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e054-128">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e054-128">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e054-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e054-129">See also</span></span>

- [<span data-ttu-id="1e054-130">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1e054-130">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1e054-131">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1e054-131">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
