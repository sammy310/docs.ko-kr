---
description: '자세히 알아보기: IMetaDataImport:: EnumSignatures 메서드'
title: IMetaDataImport::EnumSignatures 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
ms.openlocfilehash: ed41dd42151791e3d27950f30b10d91217ad7e7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771628"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="0c435-103">IMetaDataImport::EnumSignatures 메서드</span><span class="sxs-lookup"><span data-stu-id="0c435-103">IMetaDataImport::EnumSignatures Method</span></span>

<span data-ttu-id="0c435-104">현재 범위의 독립 실행형 서명을 나타내는 Signature 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="0c435-104">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c435-105">구문</span><span class="sxs-lookup"><span data-stu-id="0c435-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c435-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c435-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="0c435-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c435-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0c435-108">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c435-108">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="0c435-109">제한이 서명 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c435-109">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0c435-110">[in] `rSignatures` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0c435-110">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="0c435-111">제한이 에서 반환 된 서명 토큰의 수입니다 `rSignatures` .</span><span class="sxs-lookup"><span data-stu-id="0c435-111">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c435-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="0c435-112">Return Value</span></span>  
  
|<span data-ttu-id="0c435-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c435-113">HRESULT</span></span>|<span data-ttu-id="0c435-114">설명</span><span class="sxs-lookup"><span data-stu-id="0c435-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0c435-115">`EnumSignatures` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0c435-115">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0c435-116">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c435-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="0c435-117">이 경우는 `pcSignatures` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="0c435-117">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c435-118">설명</span><span class="sxs-lookup"><span data-stu-id="0c435-118">Remarks</span></span>  

 <span data-ttu-id="0c435-119">서명 토큰은 [IMetaDataEmit:: GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) 메서드를 통해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c435-119">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c435-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c435-120">Requirements</span></span>  

 <span data-ttu-id="0c435-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c435-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c435-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="0c435-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c435-123">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c435-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c435-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c435-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c435-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c435-125">See also</span></span>

- [<span data-ttu-id="0c435-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c435-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0c435-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c435-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
