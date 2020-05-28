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
ms.openlocfilehash: 61d81c94e3a9c092b5d45791962635c761e8da8a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008146"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="d4e74-102">IMetaDataAssemblyEmit::DefineFile 메서드</span><span class="sxs-lookup"><span data-stu-id="d4e74-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="d4e74-103">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e74-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e74-104">구문</span><span class="sxs-lookup"><span data-stu-id="d4e74-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4e74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4e74-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="d4e74-106">진행 사용할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d4e74-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="d4e74-107">진행 어셈블리와 연결 된 해시 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d4e74-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="d4e74-108">진행 의 크기 (바이트) `pbHashValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d4e74-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="d4e74-109">진행 `FileFlags`속성 설정을 지정 하는 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="d4e74-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="d4e74-110">제한이 반환 된 토큰에 대 한 포인터 `File` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d4e74-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4e74-111">설명</span><span class="sxs-lookup"><span data-stu-id="d4e74-111">Remarks</span></span>  
 <span data-ttu-id="d4e74-112">`File`메타 데이터를 포함 하는 파일을 제외 하 고이 어셈블리가 빌드된 시점에이 어셈블리의 일부인 각 파일에 대해 하나의 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e74-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4e74-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4e74-113">Requirements</span></span>  
 <span data-ttu-id="d4e74-114">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4e74-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4e74-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d4e74-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d4e74-116">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4e74-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d4e74-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4e74-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4e74-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4e74-118">See also</span></span>

- [<span data-ttu-id="d4e74-119">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4e74-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
