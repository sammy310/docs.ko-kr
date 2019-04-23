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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd0c2da234fa89bbf92c2117d6428d64502da0c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208178"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="90825-102">IMetaDataAssemblyEmit::SetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="90825-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="90825-103">지정된 `File` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="90825-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90825-104">구문</span><span class="sxs-lookup"><span data-stu-id="90825-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90825-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90825-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="90825-106">[in] 지정 된 메타 데이터 토큰을 `File` 수정할 메타 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="90825-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="90825-107">[in] 파일에 연결 된 데이터 해시에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="90825-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="90825-108">[in] 크기 (바이트) `pbHashValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="90825-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="90825-109">[in] 비트 조합 [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) 파일의 다양 한 특성을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="90825-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90825-110">설명</span><span class="sxs-lookup"><span data-stu-id="90825-110">Remarks</span></span>  
 <span data-ttu-id="90825-111">만들려는 `File` 메타 데이터 구조를 사용 합니다 [imetadataassemblyemit:: Definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="90825-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90825-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90825-112">Requirements</span></span>  
 <span data-ttu-id="90825-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="90825-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90825-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90825-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90825-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="90825-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90825-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90825-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90825-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="90825-117">See also</span></span>

- [<span data-ttu-id="90825-118">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90825-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
