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
ms.openlocfilehash: beb697d80417b937876a0887e4376341185a47d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447216"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="7e1a5-102">IMetaDataAssemblyImport::GetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="7e1a5-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="7e1a5-103">Gets the properties of the file with the specified metadata signature.</span><span class="sxs-lookup"><span data-stu-id="7e1a5-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e1a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e1a5-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7e1a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e1a5-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="7e1a5-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span><span class="sxs-lookup"><span data-stu-id="7e1a5-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="7e1a5-107">[out] The simple name of the file.</span><span class="sxs-lookup"><span data-stu-id="7e1a5-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7e1a5-108">[in] The size, in wide chars, of `szName`.</span><span class="sxs-lookup"><span data-stu-id="7e1a5-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="7e1a5-109">[out] The number of wide chars actually returned in `szName`.</span><span class="sxs-lookup"><span data-stu-id="7e1a5-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="7e1a5-110">[out] A pointer to the hash value.</span><span class="sxs-lookup"><span data-stu-id="7e1a5-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="7e1a5-111">This is the hash, using the SHA-1 algorithm, of the file.</span><span class="sxs-lookup"><span data-stu-id="7e1a5-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="7e1a5-112">[out] The number of wide chars in the returned hash value.</span><span class="sxs-lookup"><span data-stu-id="7e1a5-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="7e1a5-113">[out] A pointer to the flags that describe the metadata applied to a file.</span><span class="sxs-lookup"><span data-stu-id="7e1a5-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="7e1a5-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span><span class="sxs-lookup"><span data-stu-id="7e1a5-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e1a5-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e1a5-115">Requirements</span></span>  
 <span data-ttu-id="7e1a5-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e1a5-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e1a5-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7e1a5-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e1a5-118">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e1a5-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7e1a5-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e1a5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e1a5-120">참조</span><span class="sxs-lookup"><span data-stu-id="7e1a5-120">See also</span></span>

- [<span data-ttu-id="7e1a5-121">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e1a5-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
