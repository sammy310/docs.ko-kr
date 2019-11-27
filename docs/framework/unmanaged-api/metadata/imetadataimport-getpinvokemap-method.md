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
ms.openlocfilehash: c458fef77b49f522ca21dd5487731f4d43588cea
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437105"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="159a9-102">IMetaDataImport::GetPinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="159a9-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="159a9-103">PInvoke 호출의 대상 어셈블리를 나타내는 ModuleRef 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="159a9-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="159a9-104">구문</span><span class="sxs-lookup"><span data-stu-id="159a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="159a9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="159a9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="159a9-106">진행 PInvoke 매핑 메타 데이터를 가져올 FieldDef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="159a9-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="159a9-107">제한이 매핑에 사용 되는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="159a9-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="159a9-108">이 값은 [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) 열거형의 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="159a9-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="159a9-109">제한이 관리 되지 않는 대상 DLL의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="159a9-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="159a9-110">진행 `szImportName`의 와이드 문자 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="159a9-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="159a9-111">제한이 `szImportName`에서 반환 되는 와이드 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="159a9-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="159a9-112">제한이 관리 되지 않는 대상 개체 라이브러리를 나타내는 ModuleRef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="159a9-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="159a9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="159a9-113">Requirements</span></span>  
 <span data-ttu-id="159a9-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="159a9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="159a9-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="159a9-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="159a9-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="159a9-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="159a9-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="159a9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159a9-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="159a9-118">See also</span></span>

- [<span data-ttu-id="159a9-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="159a9-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="159a9-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="159a9-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
