---
title: IMetaDataImport::GetNestedClassProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7dd59c1e0e8b28c557910da3fd9c6489370cc62
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778957"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="db1a5-102">IMetaDataImport::GetNestedClassProps 메서드</span><span class="sxs-lookup"><span data-stu-id="db1a5-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="db1a5-103">부모에 대 한 TypeDef 토큰을 가져옵니다 <xref:System.Type> 중첩 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="db1a5-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db1a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="db1a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db1a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db1a5-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="db1a5-106">[in] 나타내는 하는 TypeDef 토큰을 <xref:System.Type> 부모 클래스를 반환 하도록 토큰에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="db1a5-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="db1a5-107">[out] 에 대 한 TypeDef 토큰에 대 한 포인터를 <xref:System.Type> 는 `tdNestedClass` 에 중첩 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db1a5-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db1a5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db1a5-108">Requirements</span></span>  
 <span data-ttu-id="db1a5-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="db1a5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db1a5-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="db1a5-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db1a5-111">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="db1a5-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="db1a5-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db1a5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1a5-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="db1a5-113">See also</span></span>

- [<span data-ttu-id="db1a5-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db1a5-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="db1a5-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db1a5-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
