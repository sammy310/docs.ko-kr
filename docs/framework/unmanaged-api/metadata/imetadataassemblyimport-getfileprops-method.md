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
ms.openlocfilehash: 0b9ff2716cc0bc32c81fe6fcdd4e6c367d4d835f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718178"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="c8b62-102">IMetaDataAssemblyImport::GetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="c8b62-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>

<span data-ttu-id="c8b62-103">지정 된 메타 데이터 시그니처를 사용 하 여 파일의 속성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8b62-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8b62-104">구문</span><span class="sxs-lookup"><span data-stu-id="c8b62-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c8b62-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8b62-105">Parameters</span></span>  

 `mdf`  
 <span data-ttu-id="c8b62-106">진행 `mdFile` 속성을 가져올 파일을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b62-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="c8b62-107">제한이 파일의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b62-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c8b62-108">진행 와이드 문자의 크기 (와이드 문자)입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="c8b62-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="c8b62-109">제한이 에서 실제로 반환 되는 와이드 문자 수입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="c8b62-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="c8b62-110">제한이 해시 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b62-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="c8b62-111">이는 파일의 SHA-1 알고리즘을 사용 하는 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b62-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="c8b62-112">제한이 반환 된 해시 값의 와이드 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b62-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="c8b62-113">제한이 파일에 적용 된 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b62-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="c8b62-114">Flags 값은 하나 이상의 [Corfileflags](corfileflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b62-114">The flags value is a combination of one or more [CorFileFlags](corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8b62-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8b62-115">Requirements</span></span>  

 <span data-ttu-id="c8b62-116">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8b62-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8b62-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c8b62-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c8b62-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b62-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c8b62-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8b62-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b62-120">참조</span><span class="sxs-lookup"><span data-stu-id="c8b62-120">See also</span></span>

- [<span data-ttu-id="c8b62-121">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8b62-121">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
