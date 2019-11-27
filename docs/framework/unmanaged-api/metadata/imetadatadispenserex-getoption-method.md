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
ms.openlocfilehash: ab74b02df959fe6e6457273e67ba3b82ae6a015c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436000"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="6e1ee-102">IMetaDataDispenserEx::GetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="6e1ee-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="6e1ee-103">현재 메타 데이터 범위에 지정 된 옵션의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="6e1ee-104">옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e1ee-105">구문</span><span class="sxs-lookup"><span data-stu-id="6e1ee-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e1ee-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e1ee-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="6e1ee-107">진행 검색할 옵션을 지정 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="6e1ee-108">지원 되는 Guid 목록은 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="6e1ee-109">제한이 반환 된 옵션의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-109">[out] The value of the returned option.</span></span> <span data-ttu-id="6e1ee-110">이 값의 형식은 지정 된 옵션 형식의 변형이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e1ee-111">주의</span><span class="sxs-lookup"><span data-stu-id="6e1ee-111">Remarks</span></span>  
 <span data-ttu-id="6e1ee-112">다음 목록에서는이 방법에 대해 지원 되는 Guid를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="6e1ee-113">설명에 대 한 자세한 내용은 [IMetaDataDispenserEx:: SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="6e1ee-114">`optionId`이 목록에 없는 경우이 메서드는 잘못 된 매개 변수를 나타내는 HRESULT `E_INVALIDARG`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="6e1ee-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="6e1ee-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="6e1ee-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="6e1ee-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="6e1ee-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="6e1ee-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="6e1ee-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="6e1ee-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="6e1ee-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="6e1ee-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="6e1ee-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="6e1ee-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="6e1ee-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="6e1ee-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e1ee-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e1ee-122">Requirements</span></span>  
 <span data-ttu-id="6e1ee-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e1ee-124">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6e1ee-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e1ee-125">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e1ee-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e1ee-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e1ee-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e1ee-127">See also</span></span>

- [<span data-ttu-id="6e1ee-128">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e1ee-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="6e1ee-129">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e1ee-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
