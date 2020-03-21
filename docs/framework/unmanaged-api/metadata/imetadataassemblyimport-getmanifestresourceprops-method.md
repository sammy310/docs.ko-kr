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
ms.openlocfilehash: d87d0d46ede65cf44c84edba92fe246174088a4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177657"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="f5bc8-102">IMetaDataAssemblyImport::GetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f5bc8-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="f5bc8-103">지정된 메타데이터 서명을 사용 하 고 매니페스트 리소스의 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f5bc8-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5bc8-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5bc8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f5bc8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5bc8-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="f5bc8-106">【인】 속성을 `mdManifestResource` 얻을 리소스를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f5bc8-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="f5bc8-107">【아웃】 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f5bc8-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f5bc8-108">【인】 크기, 와이드 문자, 의 `szName`.</span><span class="sxs-lookup"><span data-stu-id="f5bc8-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="f5bc8-109">【아웃】 실제로 반환된 와이드 문자 수에 `szName`대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5bc8-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="f5bc8-110">【아웃】 리소스를 `mdFile` 포함하는 파일 `mdAssemblyRef` 또는 어셈블리를 각각 나타내는 토큰 또는 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5bc8-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="f5bc8-111">【아웃】 오프셋을 파일 내의 리소스의 시작 부분으로 지정하는 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5bc8-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="f5bc8-112">【아웃】 리소스에 적용된 메타데이터를 설명하는 플래그에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5bc8-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="f5bc8-113">플래그 값은 하나 이상의 [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="f5bc8-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5bc8-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5bc8-114">Requirements</span></span>  
 <span data-ttu-id="f5bc8-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5bc8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5bc8-116">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="f5bc8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5bc8-117">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f5bc8-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5bc8-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5bc8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5bc8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5bc8-119">See also</span></span>

- [<span data-ttu-id="f5bc8-120">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5bc8-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
