---
title: IMetaDataAssemblyEmit::DefineAssemblyRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e480c408c10eb9e135f260426750f7747e5d8ce5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117354"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="34bd6-102">IMetaDataAssemblyEmit::DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="34bd6-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="34bd6-103">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `AssemblyRef` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34bd6-104">구문</span><span class="sxs-lookup"><span data-stu-id="34bd6-104">Syntax</span></span>  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34bd6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34bd6-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="34bd6-106">[in] 참조 된 어셈블리의 게시자의 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="34bd6-107">도우미 함수 [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) 이 매개 변수로 전달 하는 공개 키의 해시를 가져오는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="34bd6-108">[in] 크기 (바이트) `pbPublicKeyOrToken`합니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="34bd6-109">[in] 어셈블리의 사람이 읽을 수 있는 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="34bd6-110">이 값은 1024 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="34bd6-111">[in] 참조 된 어셈블리의 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="34bd6-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="34bd6-112">[in] 참조 된 어셈블리와 연결 된 해시 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="34bd6-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="34bd6-114">[in] 크기 (바이트) `pbHashValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="34bd6-115">[in] 비트 조합 [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 실행 엔진의 동작에 영향을 주는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="34bd6-116">[out] 반환 된 포인터 `AssemblyRef` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34bd6-117">설명</span><span class="sxs-lookup"><span data-stu-id="34bd6-117">Remarks</span></span>  
 <span data-ttu-id="34bd6-118">하나의 `AssemblyRef` 이 어셈블리가 참조 하는 각 어셈블리에 대 한 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="34bd6-119">런타임 시 참조 된 어셈블리의 세부 정보는 "있는 그대로" 작성"정보를 나타내는 표시를 사용 하 여 어셈블리 확인자에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="34bd6-120">어셈블리 확인자는 다음 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="34bd6-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34bd6-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34bd6-121">Requirements</span></span>  
 <span data-ttu-id="34bd6-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="34bd6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34bd6-123">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34bd6-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34bd6-124">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="34bd6-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34bd6-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34bd6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34bd6-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="34bd6-126">See also</span></span>

- [<span data-ttu-id="34bd6-127">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34bd6-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
