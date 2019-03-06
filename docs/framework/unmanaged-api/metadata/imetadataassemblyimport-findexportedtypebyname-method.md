---
title: IMetaDataAssemblyImport::FindExportedTypeByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7575659441b2eae37365c10050bca53e0cfdef6f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473918"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="09db9-102">IMetaDataAssemblyImport::FindExportedTypeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="09db9-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="09db9-103">지정 된 이름과 바깥쪽 형식 내보낸된 형식에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09db9-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09db9-104">구문</span><span class="sxs-lookup"><span data-stu-id="09db9-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09db9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09db9-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="09db9-106">[in] 내보낸 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09db9-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="09db9-107">[in] 내보낸 형식의 바깥쪽 클래스에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="09db9-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="09db9-108">이 값은 `mdExportedTypeNil` 요청한 내보낸 경우 형식이 중첩된 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="09db9-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="09db9-109">[out] 에 대 한 포인터를 `mdExportedType` 내보낸된 형식을 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="09db9-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09db9-110">설명</span><span class="sxs-lookup"><span data-stu-id="09db9-110">Remarks</span></span>  
 <span data-ttu-id="09db9-111">`FindExportedTypeByName` 메서드 참조를 확인 하는 것에 대 한 공용 언어 런타임에서 표준 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="09db9-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09db9-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09db9-112">Requirements</span></span>  
 <span data-ttu-id="09db9-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="09db9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09db9-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="09db9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09db9-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="09db9-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09db9-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09db9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09db9-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="09db9-117">See also</span></span>
- [<span data-ttu-id="09db9-118">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09db9-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="09db9-119">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="09db9-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
