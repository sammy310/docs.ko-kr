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
ms.openlocfilehash: f46033b9e643ef6b4a0063c4995b8c024b8c1f7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175358"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="400b4-102">IMetaDataImport::GetModuleRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="400b4-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="400b4-103">지정한 메타데이터 토큰에서 참조된 모듈의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="400b4-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="400b4-104">구문</span><span class="sxs-lookup"><span data-stu-id="400b4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="400b4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="400b4-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="400b4-106">【인】 모듈 참조 메타데이터 정보를 가져오는 모듈 참조 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="400b4-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="400b4-107">【아웃】 모듈 이름을 보유하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="400b4-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="400b4-108">【인】 넓은 문자의 `szName` 요청 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="400b4-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="400b4-109">【아웃】 와이드 문자의 `szName` 반환 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="400b4-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="400b4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="400b4-110">Requirements</span></span>  
 <span data-ttu-id="400b4-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="400b4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="400b4-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="400b4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="400b4-113">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="400b4-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="400b4-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="400b4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="400b4-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="400b4-115">See also</span></span>

- [<span data-ttu-id="400b4-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="400b4-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="400b4-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="400b4-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
