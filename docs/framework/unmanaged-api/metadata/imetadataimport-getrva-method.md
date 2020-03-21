---
title: IMetaDataImport::GetRVA 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: 190bcacc84646cfd9294cf2b6b53b0474f38758f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177211"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="38226-102">IMetaDataImport::GetRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="38226-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="38226-103">상대 가상 주소(RVA)와 지정된 토큰으로 표시되는 메서드 또는 필드의 구현 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38226-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38226-104">구문</span><span class="sxs-lookup"><span data-stu-id="38226-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38226-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38226-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="38226-106">【인】 RVA를 반환하는 코드 개체를 나타내는 MethodDef 또는 FieldDef 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="38226-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="38226-107">토큰이 FieldDef인 경우 필드는 전역 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38226-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="38226-108">【아웃】 토큰으로 표시되는 코드 개체의 상대가상 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="38226-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="38226-109">【아웃】 메서드에 대 한 구현 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="38226-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="38226-110">이 값은 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 열거형의 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="38226-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="38226-111">`pdwImplFlags` 값은 MethodDef 토큰인 경우에만 `tk` 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="38226-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38226-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38226-112">Requirements</span></span>  
 <span data-ttu-id="38226-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38226-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38226-114">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="38226-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38226-115">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="38226-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38226-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38226-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38226-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38226-117">See also</span></span>

- [<span data-ttu-id="38226-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38226-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="38226-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38226-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
