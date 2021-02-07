---
description: '자세히 알아보기: IMetaDataAssemblyImport:: GetManifestResourceProps 메서드'
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
ms.openlocfilehash: d8f390f8eede5153df282cc30479ceff22fb552d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728288"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="66bd4-103">IMetaDataAssemblyImport::GetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="66bd4-103">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>

<span data-ttu-id="66bd4-104">지정 된 메타 데이터 시그니처를 사용 하 여 매니페스트 리소스의 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66bd4-104">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66bd4-105">구문</span><span class="sxs-lookup"><span data-stu-id="66bd4-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="66bd4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66bd4-106">Parameters</span></span>  

 `mdmr`  
 <span data-ttu-id="66bd4-107">진행 `mdManifestResource` 속성을 가져올 리소스를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="66bd4-107">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="66bd4-108">제한이 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="66bd4-108">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="66bd4-109">진행 와이드 문자의 크기 (와이드 문자)입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="66bd4-109">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="66bd4-110">제한이 에 실제로 반환 된 와이드 문자 수에 대 한 포인터입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="66bd4-110">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="66bd4-111">제한이 `mdFile` `mdAssemblyRef` 리소스를 포함 하는 파일 또는 어셈블리를 각각 나타내는 토큰 또는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="66bd4-111">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="66bd4-112">제한이 파일 내 리소스의 시작에 대 한 오프셋을 지정 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="66bd4-112">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="66bd4-113">제한이 리소스에 적용 되는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="66bd4-113">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="66bd4-114">Flags 값은 하나 이상의 [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="66bd4-114">The flags value is a combination of one or more [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66bd4-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66bd4-115">Requirements</span></span>  

 <span data-ttu-id="66bd4-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66bd4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66bd4-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="66bd4-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66bd4-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66bd4-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66bd4-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66bd4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66bd4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66bd4-120">See also</span></span>

- [<span data-ttu-id="66bd4-121">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66bd4-121">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
