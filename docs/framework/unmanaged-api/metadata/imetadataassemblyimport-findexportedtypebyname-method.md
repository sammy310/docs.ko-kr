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
ms.openlocfilehash: 3e470250fa0e86610fcc9a6d6e2ca03569d62b54
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449453"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="e5746-102">IMetaDataAssemblyImport::FindExportedTypeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="e5746-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="e5746-103">Gets a pointer to an exported type, given its name and enclosing type.</span><span class="sxs-lookup"><span data-stu-id="e5746-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5746-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5746-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5746-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5746-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e5746-106">[in] The name of the exported type.</span><span class="sxs-lookup"><span data-stu-id="e5746-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="e5746-107">[in] The metadata token for the enclosing class of the exported type.</span><span class="sxs-lookup"><span data-stu-id="e5746-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="e5746-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span><span class="sxs-lookup"><span data-stu-id="e5746-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="e5746-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span><span class="sxs-lookup"><span data-stu-id="e5746-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5746-110">주의</span><span class="sxs-lookup"><span data-stu-id="e5746-110">Remarks</span></span>  
 <span data-ttu-id="e5746-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span><span class="sxs-lookup"><span data-stu-id="e5746-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5746-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5746-112">Requirements</span></span>  
 <span data-ttu-id="e5746-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5746-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5746-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e5746-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5746-115">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5746-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5746-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5746-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5746-117">참조</span><span class="sxs-lookup"><span data-stu-id="e5746-117">See also</span></span>

- [<span data-ttu-id="e5746-118">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5746-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="e5746-119">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="e5746-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
