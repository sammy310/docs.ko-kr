---
description: '자세히 알아보기: IMetaDataAssemblyImport:: GetExportedTypeProps 메서드'
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
ms.openlocfilehash: 894fb65fb6de76a218489b2a85a2d3c20c572789
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784121"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="c4eb0-103">IMetaDataAssemblyImport::GetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="c4eb0-103">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>

<span data-ttu-id="c4eb0-104">지정 된 메타 데이터 시그니처를 사용 하 여 내보낸 형식의 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-104">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4eb0-105">구문</span><span class="sxs-lookup"><span data-stu-id="c4eb0-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c4eb0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c4eb0-106">Parameters</span></span>  

 `mdct`  
 <span data-ttu-id="c4eb0-107">진행 `mdExportedType` 내보낸 형식을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-107">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="c4eb0-108">제한이 내보낸 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-108">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c4eb0-109">진행 의 크기 (와이드 문자)입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="c4eb0-109">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="c4eb0-110">제한이 에서 실제로 반환 된 와이드 문자의 수입니다. `szName`</span><span class="sxs-lookup"><span data-stu-id="c4eb0-110">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="c4eb0-111">제한이 `mdFile` `mdAssemblyRef` `mdExportedType` 내보낸 형식의 속성에 대 한 액세스를 포함 하거나 허용 하는, 또는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-111">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="c4eb0-112">제한이 `mdTypeDef` 파일의 형식을 나타내는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-112">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="c4eb0-113">제한이 내보낸 형식에 적용 되는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-113">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="c4eb0-114">Flags 값은 하나 이상의 [Cortypeattr](cortypeattr-enumeration.md) 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-114">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4eb0-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4eb0-115">Requirements</span></span>  

 <span data-ttu-id="c4eb0-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4eb0-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c4eb0-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4eb0-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4eb0-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4eb0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4eb0-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4eb0-120">See also</span></span>

- [<span data-ttu-id="c4eb0-121">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c4eb0-121">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
