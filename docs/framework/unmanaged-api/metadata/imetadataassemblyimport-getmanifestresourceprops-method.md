---
title: IMetaDataAssemblyImport::GetManifestResourceProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e47b1807e51427487d6af2f96ff5af437c4653eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760953"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="53a4f-102">IMetaDataAssemblyImport::GetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="53a4f-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="53a4f-103">지정 된 메타 데이터 서명 사용 하 여 매니페스트 리소스의 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="53a4f-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53a4f-104">구문</span><span class="sxs-lookup"><span data-stu-id="53a4f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53a4f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="53a4f-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="53a4f-106">[in] `mdManifestResource` 속성을 검색할 원본에 대 한 리소스를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="53a4f-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="53a4f-107">[out] 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="53a4f-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="53a4f-108">[in] 와이드 문자에서 크기의 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="53a4f-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="53a4f-109">[out] 에 실제로 반환 된 와이드 문자 수에 대 한 포인터 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="53a4f-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="53a4f-110">[out] 에 대 한 포인터를 `mdFile` 토큰 또는 `mdAssemblyRef` 리소스가 포함 된 파일 또는 어셈블리를 각각 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="53a4f-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="53a4f-111">[out] 파일 내에서 리소스의 시작 부분 까지의 오프셋을 지정 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="53a4f-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="53a4f-112">[out] 리소스에 적용할 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="53a4f-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="53a4f-113">플래그 값은 하나 이상의 조합 [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="53a4f-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53a4f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53a4f-114">Requirements</span></span>  
 <span data-ttu-id="53a4f-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="53a4f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53a4f-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="53a4f-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53a4f-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="53a4f-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53a4f-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53a4f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a4f-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="53a4f-119">See also</span></span>

- [<span data-ttu-id="53a4f-120">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53a4f-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
