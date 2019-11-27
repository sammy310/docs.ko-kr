---
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
ms.openlocfilehash: c3c57074ae53e2e1d8d41aa04cb6eb6089db58b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449435"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="24d22-102">IMetaDataAssemblyImport::GetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="24d22-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="24d22-103">지정 된 메타 데이터 시그니처를 사용 하 여 어셈블리에 대 한 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24d22-104">구문</span><span class="sxs-lookup"><span data-stu-id="24d22-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="24d22-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24d22-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="24d22-106">[in].</span><span class="sxs-lookup"><span data-stu-id="24d22-106">[in].</span></span> <span data-ttu-id="24d22-107">속성을 가져올 어셈블리를 나타내는 `mdAssembly` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="24d22-108">제한이 공개 키 또는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="24d22-109">제한이 반환 된 공개 키의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="24d22-110">제한이 어셈블리의 파일을 해시 하는 데 사용 되는 알고리즘에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="24d22-111">제한이 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="24d22-112">진행 `szName`의 크기 (와이드 문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="24d22-113">제한이 `szName`에서 실제로 반환 되는 와이드 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="24d22-114">제한이 어셈블리 메타 데이터를 포함 하는 ASSEMBLYMETADATA 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="24d22-115">제한이 어셈블리에 적용 된 메타 데이터를 설명 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="24d22-116">이 값은 하나 이상의 [Corassemblyflags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24d22-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="24d22-117">Requirements</span></span>  
 <span data-ttu-id="24d22-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24d22-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24d22-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="24d22-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24d22-120">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24d22-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24d22-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24d22-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d22-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24d22-122">See also</span></span>

- [<span data-ttu-id="24d22-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24d22-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
