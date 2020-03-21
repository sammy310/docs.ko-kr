---
title: IMetaDataEmit::SetFieldMarshal 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
ms.openlocfilehash: 1037cd4210605192870d43d88979b89af6536380
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175657"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="26de3-102">IMetaDataEmit::SetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="26de3-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="26de3-103">지정된 토큰에서 참조하는 필드, 메서드 반환 또는 메서드 매개 변수에 대한 PInvoke 마샬링 정보를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="26de3-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26de3-104">구문</span><span class="sxs-lookup"><span data-stu-id="26de3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26de3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="26de3-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="26de3-106">【인】 대상 데이터 항목에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="26de3-106">[in] The token for target data item.</span></span> <span data-ttu-id="26de3-107">이것은 또는 `mdFieldDef` 토큰입니다. `mdParamDef`</span><span class="sxs-lookup"><span data-stu-id="26de3-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="26de3-108">【인】 관리되지 않는 형식의 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="26de3-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="26de3-109">【인】 의 바이트 `pvNativeType`수입니다.</span><span class="sxs-lookup"><span data-stu-id="26de3-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26de3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26de3-110">Requirements</span></span>  
 <span data-ttu-id="26de3-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26de3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26de3-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="26de3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26de3-113">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="26de3-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26de3-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26de3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26de3-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26de3-115">See also</span></span>

- [<span data-ttu-id="26de3-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26de3-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="26de3-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26de3-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
