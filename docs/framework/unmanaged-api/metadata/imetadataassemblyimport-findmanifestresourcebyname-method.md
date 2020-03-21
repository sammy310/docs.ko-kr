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
ms.openlocfilehash: ae9097725aecd21e910e49a78d81951df39e9b2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177772"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="bbf34-102">IMetaDataAssemblyImport::FindManifestResourceByName 메서드</span><span class="sxs-lookup"><span data-stu-id="bbf34-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="bbf34-103">지정된 이름으로 매니페스트 리소스에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bbf34-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbf34-104">구문</span><span class="sxs-lookup"><span data-stu-id="bbf34-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="bbf34-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bbf34-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="bbf34-106">【인】 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bbf34-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="bbf34-107">【아웃】 메타데이터 토큰을 `mdManifestResource` 저장하는 데 사용되는 배열로, 각 토큰은 매니페스트 리소스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bbf34-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbf34-108">설명</span><span class="sxs-lookup"><span data-stu-id="bbf34-108">Remarks</span></span>  
 <span data-ttu-id="bbf34-109">이 `FindManifestResourceByName` 메서드는 참조를 해결하기 위해 공통 언어 런타임에서 사용하는 표준 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf34-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbf34-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bbf34-110">Requirements</span></span>  
 <span data-ttu-id="bbf34-111">**플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbf34-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbf34-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="bbf34-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bbf34-113">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="bbf34-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bbf34-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbf34-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf34-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bbf34-115">See also</span></span>

- [<span data-ttu-id="bbf34-116">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bbf34-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="bbf34-117">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="bbf34-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
