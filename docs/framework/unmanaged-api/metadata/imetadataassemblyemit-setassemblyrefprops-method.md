---
description: '자세히 알아보기: IMetaDataAssemblyEmit:: SetAssemblyRefProps 메서드'
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
ms.openlocfilehash: 704fff656b705bb246e2742ce991d41fcadcdfcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678174"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="33bc7-103">IMetaDataAssemblyEmit::SetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="33bc7-103">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>

<span data-ttu-id="33bc7-104">지정된 `AssemblyRef` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="33bc7-104">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33bc7-105">구문</span><span class="sxs-lookup"><span data-stu-id="33bc7-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="33bc7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="33bc7-106">Parameters</span></span>  

 `ar`  
 <span data-ttu-id="33bc7-107">진행 수정할 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다 `AssemblyRef` .</span><span class="sxs-lookup"><span data-stu-id="33bc7-107">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="33bc7-108">진행 참조 된 어셈블리의 게시자에 대 한 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="33bc7-108">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="33bc7-109">진행 의 크기 (바이트) `pbPublicKeyOrToken` 입니다.</span><span class="sxs-lookup"><span data-stu-id="33bc7-109">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="33bc7-110">진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33bc7-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="33bc7-111">진행 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="33bc7-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="33bc7-112">진행 어셈블리와 연결 된 해시 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="33bc7-112">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="33bc7-113">진행 의 크기 (바이트) `pbHashValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="33bc7-113">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="33bc7-114">진행 참조 된 어셈블리의 특성을 지정 하는 [Assemblyrefflags](assemblyrefflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="33bc7-114">[in] A bitwise combination of [AssemblyRefFlags](assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33bc7-115">설명</span><span class="sxs-lookup"><span data-stu-id="33bc7-115">Remarks</span></span>  

 <span data-ttu-id="33bc7-116">`AssemblyRef`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="33bc7-116">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33bc7-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33bc7-117">Requirements</span></span>  

 <span data-ttu-id="33bc7-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33bc7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33bc7-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="33bc7-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33bc7-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33bc7-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33bc7-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33bc7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33bc7-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33bc7-122">See also</span></span>

- [<span data-ttu-id="33bc7-123">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33bc7-123">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
