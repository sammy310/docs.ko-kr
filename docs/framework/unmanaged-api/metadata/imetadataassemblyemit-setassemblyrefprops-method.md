---
title: IMetaDataAssemblyEmit::SetAssemblyRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25d5e412dc52e4ce26995ff88454b33ccea64c89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110099"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="f88ee-102">IMetaDataAssemblyEmit::SetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f88ee-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="f88ee-103">지정된 `AssemblyRef` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f88ee-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f88ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="f88ee-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f88ee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f88ee-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="f88ee-106">[in] 지정 된 메타 데이터 토큰을 `AssemblyRef` 수정할 메타 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f88ee-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="f88ee-107">[in] 참조 된 어셈블리의 게시자의 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="f88ee-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="f88ee-108">[in] 크기 (바이트) `pbPublicKeyOrToken`합니다.</span><span class="sxs-lookup"><span data-stu-id="f88ee-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="f88ee-109">[in] 어셈블리의 사람이 읽을 수 있는 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f88ee-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="f88ee-110">[in] 어셈블리의 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f88ee-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="f88ee-111">[in] 어셈블리와 연결 된 데이터 해시에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f88ee-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="f88ee-112">[in] 크기 (바이트) `pbHashValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="f88ee-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="f88ee-113">[in] 비트 조합 [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) 참조 된 어셈블리의 특성을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f88ee-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f88ee-114">설명</span><span class="sxs-lookup"><span data-stu-id="f88ee-114">Remarks</span></span>  
 <span data-ttu-id="f88ee-115">만들려는 `AssemblyRef` 메타 데이터 구조를 사용 합니다 [imetadataassemblyemit:: Defineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f88ee-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f88ee-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f88ee-116">Requirements</span></span>  
 <span data-ttu-id="f88ee-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f88ee-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f88ee-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f88ee-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f88ee-119">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f88ee-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f88ee-120">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f88ee-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f88ee-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="f88ee-121">See also</span></span>

- [<span data-ttu-id="f88ee-122">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f88ee-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
