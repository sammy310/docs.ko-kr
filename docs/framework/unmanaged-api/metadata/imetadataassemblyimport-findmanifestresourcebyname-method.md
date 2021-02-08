---
description: '자세히 알아보기: IMetaDataAssemblyImport:: FindManifestResourceByName 메서드'
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
ms.openlocfilehash: 1d1312277675a1f2bf213221ab8d9d2a584733a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784173"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="cc1db-103">IMetaDataAssemblyImport::FindManifestResourceByName 메서드</span><span class="sxs-lookup"><span data-stu-id="cc1db-103">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>

<span data-ttu-id="cc1db-104">지정 된 이름을 사용 하 여 매니페스트 리소스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc1db-104">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc1db-105">구문</span><span class="sxs-lookup"><span data-stu-id="cc1db-105">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="cc1db-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc1db-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="cc1db-107">진행 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cc1db-107">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="cc1db-108">제한이 `mdManifestResource` 각각 매니페스트 리소스를 나타내는 메타 데이터 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="cc1db-108">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc1db-109">설명</span><span class="sxs-lookup"><span data-stu-id="cc1db-109">Remarks</span></span>  

 <span data-ttu-id="cc1db-110">`FindManifestResourceByName`메서드는 참조를 확인 하기 위해 공용 언어 런타임에서 사용 하는 표준 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc1db-110">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc1db-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc1db-111">Requirements</span></span>  

 <span data-ttu-id="cc1db-112">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc1db-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc1db-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="cc1db-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc1db-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc1db-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc1db-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc1db-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc1db-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc1db-116">See also</span></span>

- [<span data-ttu-id="cc1db-117">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc1db-117">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="cc1db-118">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="cc1db-118">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
