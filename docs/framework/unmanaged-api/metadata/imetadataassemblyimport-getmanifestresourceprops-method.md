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
ms.openlocfilehash: c1792ed0f15f8cfb62567593c9694453650f0bb9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436324"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="18cb8-102">IMetaDataAssemblyImport::GetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="18cb8-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="18cb8-103">지정 된 메타 데이터 시그니처를 사용 하 여 매니페스트 리소스의 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18cb8-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18cb8-104">구문</span><span class="sxs-lookup"><span data-stu-id="18cb8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="18cb8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18cb8-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="18cb8-106">진행 속성을 가져올 리소스를 나타내는 `mdManifestResource` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="18cb8-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="18cb8-107">제한이 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="18cb8-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="18cb8-108">진행 `szName`의 크기 (와이드 문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="18cb8-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="18cb8-109">제한이 `szName`에서 실제로 반환 되는 와이드 문자 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="18cb8-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="18cb8-110">제한이 리소스를 포함 하는 파일 또는 어셈블리를 각각 나타내는 `mdAssemblyRef` 토큰 또는 `mdFile` 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="18cb8-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="18cb8-111">제한이 파일 내 리소스의 시작에 대 한 오프셋을 지정 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="18cb8-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="18cb8-112">제한이 리소스에 적용 되는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="18cb8-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="18cb8-113">Flags 값은 하나 이상의 [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="18cb8-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18cb8-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18cb8-114">Requirements</span></span>  
 <span data-ttu-id="18cb8-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18cb8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18cb8-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="18cb8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18cb8-117">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18cb8-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18cb8-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18cb8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18cb8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18cb8-119">See also</span></span>

- [<span data-ttu-id="18cb8-120">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18cb8-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
