---
title: IMetaDataImport::GetModuleRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be4408758db1cbf7839c12cb66ff395625925f69
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779019"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="1a6bb-102">IMetaDataImport::GetModuleRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="1a6bb-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="1a6bb-103">지정한 메타데이터 토큰에서 참조된 모듈의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a6bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a6bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a6bb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a6bb-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="1a6bb-106">[in] ModuleRef 메타 데이터 토큰에 대 한 메타 데이터 정보를 가져오려는 모듈 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="1a6bb-107">[out] 모듈 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="1a6bb-108">[in] 요청된 된 크기의 `szName` 와이드 문자에서.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="1a6bb-109">[out] 반환 되는 크기의 `szName` 와이드 문자에서.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a6bb-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a6bb-110">Requirements</span></span>  
 <span data-ttu-id="1a6bb-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a6bb-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1a6bb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a6bb-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1a6bb-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1a6bb-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a6bb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a6bb-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="1a6bb-115">See also</span></span>

- [<span data-ttu-id="1a6bb-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a6bb-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1a6bb-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a6bb-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
