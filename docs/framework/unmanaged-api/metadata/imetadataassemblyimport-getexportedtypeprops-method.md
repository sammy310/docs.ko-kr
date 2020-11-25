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
ms.openlocfilehash: 32224431051b958a3f01ffeb15cdb6db1dae2657
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722104"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="ba8e3-102">IMetaDataAssemblyImport::GetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="ba8e3-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>

<span data-ttu-id="ba8e3-103">지정 된 메타 데이터 시그니처를 사용 하 여 내보낸 형식의 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ba8e3-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba8e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba8e3-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="ba8e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba8e3-105">Parameters</span></span>  

 `mdct`  
 <span data-ttu-id="ba8e3-106">진행 `mdExportedType` 내보낸 형식을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ba8e3-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="ba8e3-107">제한이 내보낸 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ba8e3-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ba8e3-108">진행 의 크기 (와이드 문자)입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="ba8e3-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ba8e3-109">제한이 에서 실제로 반환 된 와이드 문자의 수입니다. `szName`</span><span class="sxs-lookup"><span data-stu-id="ba8e3-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="ba8e3-110">제한이 `mdFile` `mdAssemblyRef` `mdExportedType` 내보낸 형식의 속성에 대 한 액세스를 포함 하거나 허용 하는, 또는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ba8e3-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="ba8e3-111">제한이 `mdTypeDef` 파일의 형식을 나타내는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba8e3-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="ba8e3-112">제한이 내보낸 형식에 적용 되는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba8e3-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="ba8e3-113">Flags 값은 하나 이상의 [Cortypeattr](cortypeattr-enumeration.md) 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba8e3-113">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba8e3-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba8e3-114">Requirements</span></span>  

 <span data-ttu-id="ba8e3-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba8e3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba8e3-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ba8e3-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba8e3-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba8e3-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba8e3-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba8e3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba8e3-119">참조</span><span class="sxs-lookup"><span data-stu-id="ba8e3-119">See also</span></span>

- [<span data-ttu-id="ba8e3-120">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba8e3-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
