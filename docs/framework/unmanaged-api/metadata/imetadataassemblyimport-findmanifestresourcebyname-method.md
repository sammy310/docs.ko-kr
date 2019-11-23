---
title: IMetaDataAssemblyImport::FindManifestResourceByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
ms.openlocfilehash: f0c390509a698fdc4682ba81182d4b407d8718c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448260"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="b8a34-102">IMetaDataAssemblyImport::FindManifestResourceByName 메서드</span><span class="sxs-lookup"><span data-stu-id="b8a34-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="b8a34-103">Gets a pointer to the manifest resource with the specified name.</span><span class="sxs-lookup"><span data-stu-id="b8a34-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8a34-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8a34-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="b8a34-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8a34-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="b8a34-106">[in] The name of the resource.</span><span class="sxs-lookup"><span data-stu-id="b8a34-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="b8a34-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span><span class="sxs-lookup"><span data-stu-id="b8a34-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8a34-108">주의</span><span class="sxs-lookup"><span data-stu-id="b8a34-108">Remarks</span></span>  
 <span data-ttu-id="b8a34-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span><span class="sxs-lookup"><span data-stu-id="b8a34-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8a34-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8a34-110">Requirements</span></span>  
 <span data-ttu-id="b8a34-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8a34-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8a34-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b8a34-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8a34-113">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8a34-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8a34-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a34-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a34-115">참조</span><span class="sxs-lookup"><span data-stu-id="b8a34-115">See also</span></span>

- [<span data-ttu-id="b8a34-116">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8a34-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="b8a34-117">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="b8a34-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
