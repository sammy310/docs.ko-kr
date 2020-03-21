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
ms.openlocfilehash: cabd6a47e5d6fc2a4cea87b16d349d9c778b3507
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176060"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="a8841-102">IMetaDataAssemblyEmit::DefineFile 메서드</span><span class="sxs-lookup"><span data-stu-id="a8841-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="a8841-103">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a8841-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8841-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8841-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8841-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8841-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="a8841-106">【인】 사용할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a8841-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="a8841-107">【인】 어셈블리와 연결된 해시 데이터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8841-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="a8841-108">【인】 의 바이트 크기입니다. `pbHashValue`</span><span class="sxs-lookup"><span data-stu-id="a8841-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="a8841-109">【인】 속성 설정을 지정하는 값의 `FileFlags` 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="a8841-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="a8841-110">【아웃】 반환된 `File` 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8841-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8841-111">설명</span><span class="sxs-lookup"><span data-stu-id="a8841-111">Remarks</span></span>  
 <span data-ttu-id="a8841-112">메타데이터가 포함된 파일을 제외하고 이 어셈블리가 빌드된 시점에 이 어셈블리의 일부였던 각 파일에 대해 하나의 `File` 메타데이터 구조를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8841-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8841-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8841-113">Requirements</span></span>  
 <span data-ttu-id="a8841-114">**플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8841-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8841-115">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="a8841-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8841-116">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a8841-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8841-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8841-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8841-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8841-118">See also</span></span>

- [<span data-ttu-id="a8841-119">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8841-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
