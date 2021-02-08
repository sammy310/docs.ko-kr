---
description: '자세히 알아보기: IMetaDataAssemblyImport:: GetAssemblyProps 메서드'
title: IMetaDataAssemblyImport::GetAssemblyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: 9cd3674dcd640bce27ae5d399d0f7de0c2eeca48
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784147"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="bf355-103">IMetaDataAssemblyImport::GetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="bf355-103">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>

<span data-ttu-id="bf355-104">지정 된 메타 데이터 시그니처를 사용 하 여 어셈블리에 대 한 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bf355-104">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf355-105">구문</span><span class="sxs-lookup"><span data-stu-id="bf355-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf355-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf355-106">Parameters</span></span>  

 `mda`  
 <span data-ttu-id="bf355-107">[in].</span><span class="sxs-lookup"><span data-stu-id="bf355-107">[in].</span></span> <span data-ttu-id="bf355-108">`mdAssembly`속성을 가져올 어셈블리를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="bf355-108">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="bf355-109">제한이 공개 키 또는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bf355-109">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="bf355-110">제한이 반환 된 공개 키의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf355-110">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="bf355-111">제한이 어셈블리의 파일을 해시 하는 데 사용 되는 알고리즘에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bf355-111">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="bf355-112">제한이 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bf355-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="bf355-113">진행 와이드 문자의 크기 (와이드 문자)입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="bf355-113">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="bf355-114">제한이 에서 실제로 반환 되는 와이드 문자 수입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="bf355-114">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="bf355-115">제한이 어셈블리 메타 데이터를 포함 하는 ASSEMBLYMETADATA 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bf355-115">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="bf355-116">제한이 어셈블리에 적용 된 메타 데이터를 설명 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="bf355-116">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="bf355-117">이 값은 하나 이상의 [Corassemblyflags](corassemblyflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="bf355-117">This value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf355-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf355-118">Requirements</span></span>  

 <span data-ttu-id="bf355-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf355-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf355-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="bf355-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf355-121">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf355-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf355-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf355-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf355-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf355-123">See also</span></span>

- [<span data-ttu-id="bf355-124">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf355-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
