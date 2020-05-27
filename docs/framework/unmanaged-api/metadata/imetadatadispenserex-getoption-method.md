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
ms.openlocfilehash: 832adacac4a6df9ccf21578538a1c557150f3ba1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008783"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="cf136-102">IMetaDataDispenserEx::GetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="cf136-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="cf136-103">현재 메타 데이터 범위에 지정 된 옵션의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf136-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="cf136-104">옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf136-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf136-105">구문</span><span class="sxs-lookup"><span data-stu-id="cf136-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf136-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf136-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="cf136-107">진행 검색할 옵션을 지정 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cf136-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="cf136-108">지원 되는 Guid 목록은 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf136-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="cf136-109">제한이 반환 된 옵션의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cf136-109">[out] The value of the returned option.</span></span> <span data-ttu-id="cf136-110">이 값의 형식은 지정 된 옵션 형식의 변형이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf136-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf136-111">설명</span><span class="sxs-lookup"><span data-stu-id="cf136-111">Remarks</span></span>  
 <span data-ttu-id="cf136-112">다음 목록에서는이 방법에 대해 지원 되는 Guid를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf136-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="cf136-113">설명에 대 한 자세한 내용은 [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf136-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="cf136-114">이 `optionId` 목록에 없는 경우이 메서드는 `E_INVALIDARG` 잘못 된 매개 변수를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf136-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="cf136-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="cf136-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="cf136-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="cf136-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="cf136-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="cf136-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="cf136-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="cf136-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="cf136-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="cf136-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="cf136-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="cf136-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="cf136-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="cf136-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf136-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf136-122">Requirements</span></span>  
 <span data-ttu-id="cf136-123">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf136-123">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf136-124">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="cf136-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf136-125">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf136-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf136-126">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf136-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf136-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf136-127">See also</span></span>

- [<span data-ttu-id="cf136-128">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf136-128">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="cf136-129">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf136-129">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
