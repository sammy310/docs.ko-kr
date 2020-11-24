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
ms.openlocfilehash: 1dd71dbe0ddb894cb5ed05c32e50429d27c66aa2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689331"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="06e94-102">IMetaDataAssemblyEmit::DefineFile 메서드</span><span class="sxs-lookup"><span data-stu-id="06e94-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>

<span data-ttu-id="06e94-103">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="06e94-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06e94-104">구문</span><span class="sxs-lookup"><span data-stu-id="06e94-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06e94-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06e94-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="06e94-106">진행 사용할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="06e94-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="06e94-107">진행 어셈블리와 연결 된 해시 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="06e94-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="06e94-108">진행 의 크기 (바이트) `pbHashValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="06e94-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="06e94-109">진행 `FileFlags` 속성 설정을 지정 하는 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="06e94-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="06e94-110">제한이 반환 된 토큰에 대 한 포인터 `File` 입니다.</span><span class="sxs-lookup"><span data-stu-id="06e94-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06e94-111">설명</span><span class="sxs-lookup"><span data-stu-id="06e94-111">Remarks</span></span>  

 <span data-ttu-id="06e94-112">`File`메타 데이터를 포함 하는 파일을 제외 하 고이 어셈블리가 빌드된 시점에이 어셈블리의 일부인 각 파일에 대해 하나의 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e94-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06e94-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06e94-113">Requirements</span></span>  

 <span data-ttu-id="06e94-114">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06e94-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06e94-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="06e94-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06e94-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e94-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06e94-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06e94-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e94-118">참조</span><span class="sxs-lookup"><span data-stu-id="06e94-118">See also</span></span>

- [<span data-ttu-id="06e94-119">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06e94-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
