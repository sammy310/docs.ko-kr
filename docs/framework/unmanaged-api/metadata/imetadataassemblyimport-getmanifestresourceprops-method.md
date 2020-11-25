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
ms.openlocfilehash: 585a9e39f529294841cd11389f03d763968a0f5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723820"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="6bd74-102">IMetaDataAssemblyImport::GetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="6bd74-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>

<span data-ttu-id="6bd74-103">지정 된 메타 데이터 시그니처를 사용 하 여 매니페스트 리소스의 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6bd74-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bd74-104">구문</span><span class="sxs-lookup"><span data-stu-id="6bd74-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6bd74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6bd74-105">Parameters</span></span>  

 `mdmr`  
 <span data-ttu-id="6bd74-106">진행 `mdManifestResource` 속성을 가져올 리소스를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd74-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="6bd74-107">제한이 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd74-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="6bd74-108">진행 와이드 문자의 크기 (와이드 문자)입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="6bd74-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="6bd74-109">제한이 에 실제로 반환 된 와이드 문자 수에 대 한 포인터입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="6bd74-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="6bd74-110">제한이 `mdFile` `mdAssemblyRef` 리소스를 포함 하는 파일 또는 어셈블리를 각각 나타내는 토큰 또는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd74-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="6bd74-111">제한이 파일 내 리소스의 시작에 대 한 오프셋을 지정 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd74-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="6bd74-112">제한이 리소스에 적용 되는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd74-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="6bd74-113">Flags 값은 하나 이상의 [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd74-113">The flags value is a combination of one or more [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bd74-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bd74-114">Requirements</span></span>  

 <span data-ttu-id="6bd74-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bd74-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bd74-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6bd74-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6bd74-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bd74-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6bd74-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bd74-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd74-119">참조</span><span class="sxs-lookup"><span data-stu-id="6bd74-119">See also</span></span>

- [<span data-ttu-id="6bd74-120">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bd74-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
