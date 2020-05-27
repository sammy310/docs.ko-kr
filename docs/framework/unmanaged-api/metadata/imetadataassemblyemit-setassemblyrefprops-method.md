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
ms.openlocfilehash: fb381a872cbeb787da0c6920f2cdeef434fb33ea
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008094"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="f8719-102">IMetaDataAssemblyEmit::SetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f8719-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="f8719-103">지정된 `AssemblyRef` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8719-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8719-104">구문</span><span class="sxs-lookup"><span data-stu-id="f8719-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f8719-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8719-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="f8719-106">진행 수정할 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다 `AssemblyRef` .</span><span class="sxs-lookup"><span data-stu-id="f8719-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="f8719-107">진행 참조 된 어셈블리의 게시자에 대 한 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="f8719-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="f8719-108">진행 의 크기 (바이트) `pbPublicKeyOrToken` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f8719-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="f8719-109">진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f8719-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="f8719-110">진행 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f8719-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="f8719-111">진행 어셈블리와 연결 된 해시 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f8719-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="f8719-112">진행 의 크기 (바이트) `pbHashValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f8719-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="f8719-113">진행 참조 된 어셈블리의 특성을 지정 하는 [Assemblyrefflags](assemblyrefflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="f8719-113">[in] A bitwise combination of [AssemblyRefFlags](assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8719-114">설명</span><span class="sxs-lookup"><span data-stu-id="f8719-114">Remarks</span></span>  
 <span data-ttu-id="f8719-115">`AssemblyRef`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8719-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8719-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8719-116">Requirements</span></span>  
 <span data-ttu-id="f8719-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8719-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8719-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f8719-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8719-119">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8719-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8719-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8719-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8719-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8719-121">See also</span></span>

- [<span data-ttu-id="f8719-122">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8719-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
