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
ms.openlocfilehash: 6ad6bbb8a4c69f575bbeba3a297c46e049a97325
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176047"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="fa197-102">IMetaDataAssemblyEmit::SetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="fa197-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="fa197-103">지정된 `AssemblyRef` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa197-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa197-104">구문</span><span class="sxs-lookup"><span data-stu-id="fa197-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="fa197-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fa197-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="fa197-106">【인】 수정할 `AssemblyRef` 메타데이터 구조를 지정하는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fa197-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="fa197-107">【인】 참조된 어셈블리의 게시자의 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fa197-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="fa197-108">【인】 의 바이트 크기입니다. `pbPublicKeyOrToken`</span><span class="sxs-lookup"><span data-stu-id="fa197-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="fa197-109">【인】 어셈블리의 사람이 읽을 수 있는 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fa197-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="fa197-110">【인】 어셈블리에 대한 버전, 플랫폼 및 로캘 정보를 포함하는 ASSEMBLYMETADATA 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fa197-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="fa197-111">【인】 어셈블리와 연결된 해시 데이터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fa197-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="fa197-112">【인】 의 바이트 크기입니다. `pbHashValue`</span><span class="sxs-lookup"><span data-stu-id="fa197-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="fa197-113">【인】 참조된 어셈블리의 특성을 지정하는 [어셈블리 RefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="fa197-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa197-114">설명</span><span class="sxs-lookup"><span data-stu-id="fa197-114">Remarks</span></span>  
 <span data-ttu-id="fa197-115">`AssemblyRef` 메타데이터 구조를 만들려면 [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa197-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa197-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa197-116">Requirements</span></span>  
 <span data-ttu-id="fa197-117">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa197-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa197-118">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="fa197-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa197-119">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="fa197-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa197-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa197-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa197-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa197-121">See also</span></span>

- [<span data-ttu-id="fa197-122">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa197-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
