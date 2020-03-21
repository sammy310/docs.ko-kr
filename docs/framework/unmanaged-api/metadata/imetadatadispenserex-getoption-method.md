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
ms.openlocfilehash: 816e2f2dc7d4d00f74f67720ee45d7b3483e57fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177728"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="5c2a8-102">IMetaDataDispenserEx::GetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="5c2a8-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="5c2a8-103">현재 메타데이터 범위에 대해 지정된 옵션의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5c2a8-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="5c2a8-104">이 옵션은 현재 메타데이터 범위에 대한 호출을 처리하는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5c2a8-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c2a8-105">구문</span><span class="sxs-lookup"><span data-stu-id="5c2a8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c2a8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c2a8-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="5c2a8-107">【인】 검색할 옵션을 지정하는 GUID에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c2a8-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="5c2a8-108">지원되는 GUID 목록은 비고 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c2a8-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5c2a8-109">【아웃】 반환된 옵션의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5c2a8-109">[out] The value of the returned option.</span></span> <span data-ttu-id="5c2a8-110">이 값의 형식은 지정된 옵션 형식의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="5c2a8-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c2a8-111">설명</span><span class="sxs-lookup"><span data-stu-id="5c2a8-111">Remarks</span></span>  
 <span data-ttu-id="5c2a8-112">다음 목록은 이 메서드에 대해 지원되는 GUID를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c2a8-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="5c2a8-113">설명은 [IMetaData에이터Ex:SetOption 메서드를](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c2a8-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="5c2a8-114">이 `optionId` 목록에 없는 경우 이 메서드는 `E_INVALIDARG`잘못된 매개 변수를 나타내는 HRESULT를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5c2a8-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="5c2a8-115">메타데이터체크중복</span><span class="sxs-lookup"><span data-stu-id="5c2a8-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="5c2a8-116">메타데이터레프토데프체크</span><span class="sxs-lookup"><span data-stu-id="5c2a8-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="5c2a8-117">메타 데이터 알림토큰 이동</span><span class="sxs-lookup"><span data-stu-id="5c2a8-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="5c2a8-118">메타데이터세텐</span><span class="sxs-lookup"><span data-stu-id="5c2a8-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="5c2a8-119">메타데이터오류이엠티아웃오브오더</span><span class="sxs-lookup"><span data-stu-id="5c2a8-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="5c2a8-120">메타데이터생성TCE어댑터</span><span class="sxs-lookup"><span data-stu-id="5c2a8-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="5c2a8-121">메타데이터링커옵션</span><span class="sxs-lookup"><span data-stu-id="5c2a8-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c2a8-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c2a8-122">Requirements</span></span>  
 <span data-ttu-id="5c2a8-123">**플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c2a8-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c2a8-124">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="5c2a8-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c2a8-125">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5c2a8-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c2a8-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c2a8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c2a8-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c2a8-127">See also</span></span>

- [<span data-ttu-id="5c2a8-128">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c2a8-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="5c2a8-129">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c2a8-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
