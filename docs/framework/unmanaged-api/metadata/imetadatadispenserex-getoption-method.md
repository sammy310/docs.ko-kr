---
title: IMetaDataDispenserEx::GetOption 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe9bc9aea4ceb0f5b5c03416f43894b482c3294e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044293"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="c409b-102">IMetaDataDispenserEx::GetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="c409b-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="c409b-103">현재 메타 데이터 범위에 대 한 지정된 된 옵션의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c409b-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="c409b-104">현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c409b-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c409b-105">구문</span><span class="sxs-lookup"><span data-stu-id="c409b-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c409b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c409b-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="c409b-107">[in] 검색할 옵션을 지정 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c409b-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="c409b-108">지원 되는 Guid의 목록은 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c409b-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="c409b-109">[out] 반환 된 옵션의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c409b-109">[out] The value of the returned option.</span></span> <span data-ttu-id="c409b-110">이 값의 형식 지정된 옵션의 종류의 변형 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c409b-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c409b-111">설명</span><span class="sxs-lookup"><span data-stu-id="c409b-111">Remarks</span></span>  
 <span data-ttu-id="c409b-112">다음은이 메서드에 대 한 지원 되는 Guid를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c409b-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="c409b-113">설명에 대 한 참조를 [imetadatadispenserex:: Setoption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c409b-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="c409b-114">하는 경우 `optionId` 는이 목록에 없는이 메서드는 HRESULT를 반환 `E_INVALIDARG`, 잘못 된 매개 변수를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="c409b-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="c409b-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="c409b-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="c409b-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="c409b-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="c409b-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="c409b-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="c409b-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="c409b-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="c409b-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="c409b-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="c409b-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="c409b-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="c409b-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="c409b-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c409b-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c409b-122">Requirements</span></span>  
 <span data-ttu-id="c409b-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c409b-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c409b-124">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c409b-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c409b-125">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="c409b-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c409b-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c409b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c409b-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="c409b-127">See also</span></span>

- [<span data-ttu-id="c409b-128">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c409b-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="c409b-129">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c409b-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
