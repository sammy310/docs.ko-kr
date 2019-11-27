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
ms.openlocfilehash: 0b7ca6f9878ed2fa2d90ea93e5101f0a66ec2d5e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440212"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="7f1c9-102">IMetaDataAssemblyEmit::DefineFile 메서드</span><span class="sxs-lookup"><span data-stu-id="7f1c9-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="7f1c9-103">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c9-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f1c9-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f1c9-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f1c9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f1c9-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="7f1c9-106">진행 사용할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c9-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="7f1c9-107">진행 어셈블리와 연결 된 해시 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c9-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="7f1c9-108">진행 `pbHashValue`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c9-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="7f1c9-109">진행 속성 설정을 지정 하는 `FileFlags` 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c9-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="7f1c9-110">제한이 반환 된 `File` 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c9-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f1c9-111">주의</span><span class="sxs-lookup"><span data-stu-id="7f1c9-111">Remarks</span></span>  
 <span data-ttu-id="7f1c9-112">메타 데이터가 포함 된 파일을 제외 하 고이 어셈블리가 빌드된 시점에이 어셈블리의 일부인 각 파일에 대해 하나의 `File` 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c9-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f1c9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f1c9-113">Requirements</span></span>  
 <span data-ttu-id="7f1c9-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f1c9-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f1c9-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7f1c9-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f1c9-116">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c9-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f1c9-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f1c9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f1c9-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f1c9-118">See also</span></span>

- [<span data-ttu-id="7f1c9-119">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f1c9-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
