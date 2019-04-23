---
title: IMetaDataAssemblyEmit::DefineFile 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5693da3b5e6d883efd9ad8a5a409a5dba8dd8b6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203433"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="0a2ed-102">IMetaDataAssemblyEmit::DefineFile 메서드</span><span class="sxs-lookup"><span data-stu-id="0a2ed-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="0a2ed-103">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ed-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a2ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a2ed-104">Syntax</span></span>  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a2ed-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a2ed-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="0a2ed-106">[in] 사용할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ed-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="0a2ed-107">[in] 어셈블리와 연결 된 데이터 해시에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ed-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="0a2ed-108">[in] 크기 (바이트) `pbHashValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ed-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="0a2ed-109">[in] 비트 조합 `FileFlags` 속성 설정을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ed-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="0a2ed-110">[out] 반환 된 포인터 `File` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ed-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a2ed-111">설명</span><span class="sxs-lookup"><span data-stu-id="0a2ed-111">Remarks</span></span>  
 <span data-ttu-id="0a2ed-112">하나의 `File` 이 어셈블리는 메타 데이터가 포함 된 파일 제외 하 고 작성 된 당시에이 어셈블리의 일부인 각 파일에 대 한 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ed-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a2ed-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a2ed-113">Requirements</span></span>  
 <span data-ttu-id="0a2ed-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a2ed-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a2ed-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a2ed-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a2ed-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0a2ed-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a2ed-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a2ed-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a2ed-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a2ed-118">See also</span></span>

- [<span data-ttu-id="0a2ed-119">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a2ed-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
