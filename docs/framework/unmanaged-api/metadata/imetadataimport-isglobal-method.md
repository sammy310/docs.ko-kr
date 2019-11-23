---
title: IMetaDataImport::IsGlobal 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
ms.openlocfilehash: 8a5dda5861343865a139f6b6b9e2794179b0727a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434721"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="56573-102">IMetaDataImport::IsGlobal 메서드</span><span class="sxs-lookup"><span data-stu-id="56573-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="56573-103">지정한 메타데이터 토큰이 나타내는 필드, 메서드 또는 형식에 전역 범위가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="56573-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56573-104">구문</span><span class="sxs-lookup"><span data-stu-id="56573-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56573-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="56573-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="56573-106">[in] A metadata token that represents a type, field, or method.</span><span class="sxs-lookup"><span data-stu-id="56573-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="56573-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="56573-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56573-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56573-108">Requirements</span></span>  
 <span data-ttu-id="56573-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56573-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56573-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="56573-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="56573-111">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="56573-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="56573-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56573-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56573-113">참조</span><span class="sxs-lookup"><span data-stu-id="56573-113">See also</span></span>

- [<span data-ttu-id="56573-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56573-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="56573-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56573-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
