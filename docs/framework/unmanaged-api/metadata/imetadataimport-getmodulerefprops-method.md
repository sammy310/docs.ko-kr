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
ms.openlocfilehash: dce9b9c20cbc73c6a70a34afa6c348c23164ed9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437324"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="4b56e-102">IMetaDataImport::GetModuleRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="4b56e-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="4b56e-103">지정한 메타데이터 토큰에서 참조된 모듈의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4b56e-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b56e-104">구문</span><span class="sxs-lookup"><span data-stu-id="4b56e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b56e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b56e-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="4b56e-106">진행 메타 데이터 정보를 가져올 모듈을 참조 하는 ModuleRef metadata 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56e-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="4b56e-107">제한이 모듈 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56e-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4b56e-108">진행 `szName`의 요청 된 크기 (와이드 문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56e-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="4b56e-109">제한이 반환 되는 `szName` 크기 (와이드 문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56e-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b56e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b56e-110">Requirements</span></span>  
 <span data-ttu-id="4b56e-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b56e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b56e-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4b56e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b56e-113">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b56e-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b56e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b56e-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="4b56e-115">See also</span></span>

- [<span data-ttu-id="4b56e-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b56e-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4b56e-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b56e-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
