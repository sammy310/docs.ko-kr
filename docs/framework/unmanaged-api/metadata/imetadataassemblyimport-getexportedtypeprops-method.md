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
ms.openlocfilehash: 15b58e01d4ce99f19f510c760819471b84380b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177765"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="32d5f-102">IMetaDataAssemblyImport::GetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="32d5f-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="32d5f-103">지정된 메타데이터 서명을 사용 하 고 내보낸된 형식의 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32d5f-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d5f-104">구문</span><span class="sxs-lookup"><span data-stu-id="32d5f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="32d5f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32d5f-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="32d5f-106">【인】 내보낸 형식을 나타내는 `mdExportedType` 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="32d5f-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="32d5f-107">【아웃】 내보낸 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="32d5f-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="32d5f-108">【인】 크기, 넓은 문자, `szName`의 .</span><span class="sxs-lookup"><span data-stu-id="32d5f-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="32d5f-109">【아웃】 실제로 반환된 와이드 문자 의 수`szName`</span><span class="sxs-lookup"><span data-stu-id="32d5f-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="32d5f-110">【아웃】 내보낸 `mdAssemblyRef`형식의 속성에 대한 액세스를 포함하거나 허용하는 `mdExportedType` `mdFile`메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="32d5f-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="32d5f-111">【아웃】 파일의 형식을 `mdTypeDef` 나타내는 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="32d5f-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="32d5f-112">【아웃】 내보낸 형식에 적용된 메타데이터를 설명하는 플래그에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="32d5f-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="32d5f-113">플래그 값은 하나 이상의 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32d5f-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32d5f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32d5f-114">Requirements</span></span>  
 <span data-ttu-id="32d5f-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32d5f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32d5f-116">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="32d5f-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32d5f-117">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="32d5f-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32d5f-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32d5f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d5f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32d5f-119">See also</span></span>

- [<span data-ttu-id="32d5f-120">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32d5f-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
