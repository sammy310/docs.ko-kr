---
title: IMetaDataAssemblyEmit::DefineManifestResource 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 026f5efe195cdb34999b65c5f47de6f68d30e11a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008133"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="a6fdc-102">IMetaDataAssemblyEmit::DefineManifestResource 메서드</span><span class="sxs-lookup"><span data-stu-id="a6fdc-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="a6fdc-103">지정된 매니페스트 리소스에 대한 메타데이터를 포함하는 `ManifestResource` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6fdc-104">구문</span><span class="sxs-lookup"><span data-stu-id="a6fdc-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6fdc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a6fdc-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="a6fdc-106">진행 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="a6fdc-107">진행 `mdtFile` `mdtAssemblyRef` 리소스 공급자에 매핑되는 또는 형식의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="a6fdc-108">NULL 값은 메타 데이터가 포함 된 파일이 리소스 공급자 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="a6fdc-109">진행 파일 내 리소스의 시작에 대 한 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="a6fdc-110">독립 실행형 파일의 리소스는 항상 0입니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="a6fdc-111">리소스가 PE (이식 가능한 실행 파일) 파일에 포함 된 경우이는 cor 헤더 파일에 지정 된 위치에서 시작 하는 리소스 BLOB의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="a6fdc-112">진행 리소스 정의에 대 한 속성 설정을 지정 하는 플래그 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="a6fdc-113">제한이 반환 된 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6fdc-114">설명</span><span class="sxs-lookup"><span data-stu-id="a6fdc-114">Remarks</span></span>  
 <span data-ttu-id="a6fdc-115">`ManifestResource`각 어셈블리 파일에서 구현 되는 각 리소스에 대해 하나의 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6fdc-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6fdc-116">Requirements</span></span>  
 <span data-ttu-id="a6fdc-117">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-117">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6fdc-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="a6fdc-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6fdc-119">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6fdc-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6fdc-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6fdc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6fdc-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6fdc-121">See also</span></span>

- [<span data-ttu-id="a6fdc-122">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6fdc-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
