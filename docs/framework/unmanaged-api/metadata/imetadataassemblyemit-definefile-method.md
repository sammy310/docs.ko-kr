---
description: IMetaDataAssemblyEmit::D efineFile 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 825ef44c2b0a5f312b4c5f9c851d62e75709c7ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671052"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="c2158-103">IMetaDataAssemblyEmit::DefineFile 메서드</span><span class="sxs-lookup"><span data-stu-id="c2158-103">IMetaDataAssemblyEmit::DefineFile Method</span></span>

<span data-ttu-id="c2158-104">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c2158-104">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2158-105">구문</span><span class="sxs-lookup"><span data-stu-id="c2158-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2158-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2158-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="c2158-107">진행 사용할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2158-107">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="c2158-108">진행 어셈블리와 연결 된 해시 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2158-108">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="c2158-109">진행 의 크기 (바이트) `pbHashValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c2158-109">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="c2158-110">진행 `FileFlags` 속성 설정을 지정 하는 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="c2158-110">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="c2158-111">제한이 반환 된 토큰에 대 한 포인터 `File` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c2158-111">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2158-112">설명</span><span class="sxs-lookup"><span data-stu-id="c2158-112">Remarks</span></span>  

 <span data-ttu-id="c2158-113">`File`메타 데이터를 포함 하는 파일을 제외 하 고이 어셈블리가 빌드된 시점에이 어셈블리의 일부인 각 파일에 대해 하나의 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2158-113">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2158-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2158-114">Requirements</span></span>  

 <span data-ttu-id="c2158-115">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2158-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2158-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c2158-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2158-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2158-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2158-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2158-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2158-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2158-119">See also</span></span>

- [<span data-ttu-id="c2158-120">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2158-120">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
