---
title: IMetaDataAssemblyImport::GetExportedTypeProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91b1e4469f07954dc433769911c78d72bb3c36cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096152"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="0c0dc-102">IMetaDataAssemblyImport::GetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="0c0dc-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="0c0dc-103">지정 된 메타 데이터 서명 사용 하 여 내보낸 형식의 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c0dc-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c0dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c0dc-104">Syntax</span></span>  
  
```  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c0dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c0dc-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="0c0dc-106">[in] `mdExportedType` 내보낸된 형식을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0c0dc-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="0c0dc-107">[out] 내보낸 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0c0dc-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0c0dc-108">[in] 와이드 문자에서 크기의 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="0c0dc-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="0c0dc-109">[out] 에 실제로 반환 된 와이드 문자 수</span><span class="sxs-lookup"><span data-stu-id="0c0dc-109">[out] The number of wide characters actually returned in</span></span> `szName`  
  
 `ptkImplementation`  
 <span data-ttu-id="0c0dc-110">[out] `mdFile`, `mdAssemblyRef`, 또는 `mdExportedType` 내보낸 형식의 속성에 대 한 액세스를 허용 또는 포함 된 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0c0dc-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="0c0dc-111">[out] 에 대 한 포인터를 `mdTypeDef` 파일의 형식을 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0c0dc-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="0c0dc-112">[out] 내보낸된 형식에 적용 하는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c0dc-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="0c0dc-113">하나 이상의 플래그 값이 될 수 있습니다 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0c0dc-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c0dc-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c0dc-114">Requirements</span></span>  
 <span data-ttu-id="0c0dc-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c0dc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c0dc-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c0dc-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c0dc-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0c0dc-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0c0dc-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="0c0dc-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c0dc-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c0dc-119">See also</span></span>

- [<span data-ttu-id="0c0dc-120">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c0dc-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
