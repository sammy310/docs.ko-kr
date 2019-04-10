---
title: IMetaDataImport::FindTypeRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: acc006894f05536ed76bac60b0fde9277a460813
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199026"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="1de94-102">IMetaDataImport::FindTypeRef 메서드</span><span class="sxs-lookup"><span data-stu-id="1de94-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="1de94-103">에 대 한 토큰은 TypeRef에 포인터를 가져옵니다는 <xref:System.Type> 지정된 된 범위에 있고 지정 된 이름을 가진 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de94-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de94-104">구문</span><span class="sxs-lookup"><span data-stu-id="1de94-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1de94-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1de94-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="1de94-106">[in] 모듈, 어셈블리 또는 형식을 나타내는 ModuleRef, AssemblyRef를 또는 TypeRef 토큰을 각각 형식이 참조 하는 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de94-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="1de94-107">[in] 검색할 형식 참조의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1de94-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="1de94-108">[out] 일치 하는 TypeRef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1de94-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de94-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1de94-109">Requirements</span></span>  
 <span data-ttu-id="1de94-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1de94-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de94-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1de94-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1de94-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1de94-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1de94-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="1de94-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1de94-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="1de94-114">See also</span></span>

- [<span data-ttu-id="1de94-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1de94-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1de94-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1de94-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
