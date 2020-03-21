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
ms.openlocfilehash: dfa900e2184a8c415d75f5702c572b14c4018749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177792"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="a4632-102">IMetaDataAssemblyImport::GetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a4632-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="a4632-103">지정된 메타데이터 서명을 통해 어셈블리에 대한 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4632-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4632-104">구문</span><span class="sxs-lookup"><span data-stu-id="a4632-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a4632-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4632-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="a4632-106">[에서].</span><span class="sxs-lookup"><span data-stu-id="a4632-106">[in].</span></span> <span data-ttu-id="a4632-107">속성을 `mdAssembly` 가져오는 어셈블리를 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a4632-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="a4632-108">【아웃】 공개 키 또는 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4632-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="a4632-109">【아웃】 반환된 공개 키의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4632-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="a4632-110">【아웃】 어셈블리의 파일을 해시하는 데 사용되는 알고리즘에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4632-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="a4632-111">【아웃】 어셈블리의 간단한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a4632-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a4632-112">【인】 크기, 와이드 문자, 의 `szName`.</span><span class="sxs-lookup"><span data-stu-id="a4632-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="a4632-113">【아웃】 와이드 문자의 수는 실제로 `szName`에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4632-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="a4632-114">【아웃】 어셈블리 메타데이터가 포함된 ASSEMBLYMETADATA 구조에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4632-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="a4632-115">【아웃】 어셈블리에 적용된 메타데이터를 설명하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="a4632-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="a4632-116">이 값은 하나 이상의 [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 플래그 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="a4632-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4632-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4632-117">Requirements</span></span>  
 <span data-ttu-id="a4632-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4632-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4632-119">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="a4632-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4632-120">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a4632-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4632-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4632-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4632-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4632-122">See also</span></span>

- [<span data-ttu-id="a4632-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4632-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
