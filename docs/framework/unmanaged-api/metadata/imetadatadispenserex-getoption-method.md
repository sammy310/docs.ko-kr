---
description: 'IMetaDataDispenserEx:: GetOption 메서드에 대해 자세히 알아보세요.'
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
ms.openlocfilehash: cf52a251c3c0e0485558a150b727d58eeae81995
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753551"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="8abba-103">IMetaDataDispenserEx::GetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="8abba-103">IMetaDataDispenserEx::GetOption Method</span></span>

<span data-ttu-id="8abba-104">현재 메타 데이터 범위에 지정 된 옵션의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8abba-104">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="8abba-105">옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8abba-105">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8abba-106">구문</span><span class="sxs-lookup"><span data-stu-id="8abba-106">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8abba-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8abba-107">Parameters</span></span>  

 `optionId`  
 <span data-ttu-id="8abba-108">진행 검색할 옵션을 지정 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8abba-108">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="8abba-109">지원 되는 Guid 목록은 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8abba-109">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="8abba-110">제한이 반환 된 옵션의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8abba-110">[out] The value of the returned option.</span></span> <span data-ttu-id="8abba-111">이 값의 형식은 지정 된 옵션 형식의 변형이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abba-111">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8abba-112">설명</span><span class="sxs-lookup"><span data-stu-id="8abba-112">Remarks</span></span>  

 <span data-ttu-id="8abba-113">다음 목록에서는이 방법에 대해 지원 되는 Guid를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8abba-113">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="8abba-114">설명에 대 한 자세한 내용은 [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8abba-114">For descriptions, see the [IMetaDataDispenserEx::SetOption](imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="8abba-115">이 `optionId` 목록에 없는 경우이 메서드는 `E_INVALIDARG` 잘못 된 매개 변수를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8abba-115">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="8abba-116">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="8abba-116">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="8abba-117">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="8abba-117">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="8abba-118">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="8abba-118">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="8abba-119">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="8abba-119">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="8abba-120">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="8abba-120">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="8abba-121">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="8abba-121">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="8abba-122">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="8abba-122">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8abba-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8abba-123">Requirements</span></span>  

 <span data-ttu-id="8abba-124">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8abba-124">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8abba-125">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8abba-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8abba-126">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abba-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8abba-127">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8abba-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8abba-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8abba-128">See also</span></span>

- [<span data-ttu-id="8abba-129">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8abba-129">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="8abba-130">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8abba-130">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
