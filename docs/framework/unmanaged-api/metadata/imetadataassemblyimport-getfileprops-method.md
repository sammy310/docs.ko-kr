---
title: IMetaDataAssemblyImport::GetFileProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: dae4a36537eeac58ffb17ebc1b78d935ec807cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175982"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="3683a-102">IMetaDataAssemblyImport::GetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="3683a-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="3683a-103">지정된 메타데이터 서명이 있는 파일의 속성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3683a-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3683a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3683a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3683a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3683a-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="3683a-106">【인】 속성을 `mdFile` 가져오는 파일을 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3683a-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="3683a-107">【아웃】 파일의 간단한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3683a-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="3683a-108">【인】 크기, 와이드 문자, 의 `szName`.</span><span class="sxs-lookup"><span data-stu-id="3683a-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="3683a-109">【아웃】 와이드 문자의 수는 실제로 `szName`에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3683a-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="3683a-110">【아웃】 해시 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3683a-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="3683a-111">이것은 파일의 SHA-1 알고리즘을 사용하는 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="3683a-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="3683a-112">【아웃】 반환된 해시 값의 와이드 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3683a-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="3683a-113">【아웃】 파일에 적용된 메타데이터를 설명하는 플래그에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3683a-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="3683a-114">플래그 값은 하나 이상의 [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="3683a-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3683a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3683a-115">Requirements</span></span>  
 <span data-ttu-id="3683a-116">**플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3683a-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3683a-117">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="3683a-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3683a-118">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3683a-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3683a-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3683a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3683a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3683a-120">See also</span></span>

- [<span data-ttu-id="3683a-121">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3683a-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
