---
title: IMetaDataAssemblyEmit::SetFileProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 106ffeee521f69a73628b1fb6a611abc733583f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431878"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="2aa47-102">IMetaDataAssemblyEmit::SetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="2aa47-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="2aa47-103">지정된 `File` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="2aa47-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aa47-104">구문</span><span class="sxs-lookup"><span data-stu-id="2aa47-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2aa47-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2aa47-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="2aa47-106">진행 수정할 `File` 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2aa47-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="2aa47-107">진행 파일과 연결 된 해시 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2aa47-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="2aa47-108">진행 `pbHashValue`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="2aa47-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="2aa47-109">진행 파일의 다양 한 특성을 지정 하는 [Corfileflags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="2aa47-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2aa47-110">설명</span><span class="sxs-lookup"><span data-stu-id="2aa47-110">Remarks</span></span>  
 <span data-ttu-id="2aa47-111">`File` 메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aa47-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aa47-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2aa47-112">Requirements</span></span>  
 <span data-ttu-id="2aa47-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2aa47-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aa47-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="2aa47-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2aa47-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aa47-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2aa47-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aa47-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa47-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="2aa47-117">See also</span></span>

- [<span data-ttu-id="2aa47-118">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2aa47-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
