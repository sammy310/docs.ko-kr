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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9842108e9a26d7cca621c06b8ae1713e17c97ebe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476362"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="57285-102">IMetaDataEmit::SetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="57285-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="57285-103">지정 된 토큰에서 참조 필드, 메서드 반환 되는 경우 또는 메서드 매개 변수에 대 한 마샬링 정보는 PInvoke를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57285-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57285-104">구문</span><span class="sxs-lookup"><span data-stu-id="57285-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57285-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="57285-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="57285-106">[in] 대상 데이터 항목에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="57285-106">[in] The token for target data item.</span></span> <span data-ttu-id="57285-107">이 값은 `mdFieldDef` 또는 `mdParamDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="57285-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="57285-108">[in] 관리 되지 않는 형식에 대 한 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="57285-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="57285-109">[in] 바이트 수가 `pvNativeType`합니다.</span><span class="sxs-lookup"><span data-stu-id="57285-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57285-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="57285-110">Requirements</span></span>  
 <span data-ttu-id="57285-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="57285-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57285-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="57285-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57285-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="57285-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57285-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57285-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57285-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="57285-115">See also</span></span>
- [<span data-ttu-id="57285-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="57285-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="57285-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="57285-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
