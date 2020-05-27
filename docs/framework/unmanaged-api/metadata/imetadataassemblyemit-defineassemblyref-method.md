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
ms.openlocfilehash: 612463bca18c23fac0b086adde2d208a0fbc5ae5
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008172"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="2238c-102">IMetaDataAssemblyEmit::DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="2238c-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="2238c-103">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `AssemblyRef` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2238c-104">구문</span><span class="sxs-lookup"><span data-stu-id="2238c-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="2238c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2238c-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="2238c-106">진행 참조 된 어셈블리의 게시자에 대 한 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="2238c-107">도우미 함수 [StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md) 를 사용 하 여이 매개 변수로 전달할 공개 키의 해시를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-107">The helper function [StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="2238c-108">진행 의 크기 (바이트) `pbPublicKeyOrToken` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="2238c-109">진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="2238c-110">이 값은 1024 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="2238c-111">진행 참조 된 어셈블리의 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="2238c-112">진행 참조 된 어셈블리와 연결 된 해시 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="2238c-113">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2238c-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="2238c-114">진행 의 크기 (바이트) `pbHashValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="2238c-115">진행 실행 엔진의 동작에 영향을 주는 [Corassemblyflags](corassemblyflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-115">[in] A bitwise combination of [CorAssemblyFlags](corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="2238c-116">제한이 반환 된 메타 데이터 토큰에 대 한 포인터 `AssemblyRef` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2238c-117">설명</span><span class="sxs-lookup"><span data-stu-id="2238c-117">Remarks</span></span>  
 <span data-ttu-id="2238c-118">`AssemblyRef`이 어셈블리가 참조 하는 각 어셈블리에 대해 하나의 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="2238c-119">런타임에 참조 된 어셈블리의 세부 정보는 "빌드" 정보를 나타내는 것으로 어셈블리 확인자에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="2238c-120">그런 다음 어셈블리 확인자는 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2238c-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2238c-121">Requirements</span></span>  
 <span data-ttu-id="2238c-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2238c-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2238c-123">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="2238c-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2238c-124">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2238c-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2238c-125">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2238c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2238c-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2238c-126">See also</span></span>

- [<span data-ttu-id="2238c-127">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2238c-127">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
