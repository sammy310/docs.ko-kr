---
title: IMetaDataImport::GetPinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99aea385cf5e3c8bcf7cf39b7cc5618f99f8a631
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777587"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="9bf41-102">IMetaDataImport::GetPinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="9bf41-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="9bf41-103">PInvoke 호출의 대상 어셈블리를 나타내는 ModuleRef 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bf41-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bf41-104">구문</span><span class="sxs-lookup"><span data-stu-id="9bf41-104">Syntax</span></span>  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bf41-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9bf41-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9bf41-106">[in] 에 대 한 PInvoke 매핑 메타 데이터를 가져올 FieldDef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf41-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="9bf41-107">[out] 매핑에 사용 되는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf41-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="9bf41-108">이 값은의 비트 마스크를 [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf41-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="9bf41-109">[out] 관리 되지 않는 대상 DLL의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf41-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="9bf41-110">[in] 와이드 문자에서 크기 `szImportName`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf41-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="9bf41-111">[out] 반환 하는 와이드 문자 수가 `szImportName`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf41-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="9bf41-112">[out] 관리 되지 않는 대상 개체 라이브러리를 나타내는 ModuleRef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf41-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bf41-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bf41-113">Requirements</span></span>  
 <span data-ttu-id="9bf41-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bf41-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bf41-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9bf41-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9bf41-116">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9bf41-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9bf41-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bf41-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf41-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="9bf41-118">See also</span></span>

- [<span data-ttu-id="9bf41-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bf41-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9bf41-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bf41-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
