---
title: IMetaDataImport::GetTypeRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4d8829c9cb2818eafe98809c9a0d5fd8109d076
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778823"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="be4db-102">IMetaDataImport::GetTypeRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="be4db-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="be4db-103">연관 된 메타 데이터를 가져옵니다는 <xref:System.Type> 지정한 TypeRef 토큰이 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4db-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be4db-104">구문</span><span class="sxs-lookup"><span data-stu-id="be4db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be4db-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="be4db-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="be4db-106">[in] TypeRef 토큰에 대 한 메타 데이터를 반환할 형식을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="be4db-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="be4db-107">[out] 참조 된 범위에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="be4db-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="be4db-108">이 값은 AssemblyRef 또는 ModuleRef 토큰을 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4db-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="be4db-109">[out] 형식 이름을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="be4db-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="be4db-110">[in] 요청된 된 크기의 와이드 문자에서 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="be4db-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="be4db-111">[out] 반환 되는 크기의 와이드 문자에서 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="be4db-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be4db-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be4db-112">Requirements</span></span>  
 <span data-ttu-id="be4db-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="be4db-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be4db-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="be4db-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be4db-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="be4db-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="be4db-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be4db-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4db-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="be4db-117">See also</span></span>

- [<span data-ttu-id="be4db-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be4db-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="be4db-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be4db-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
