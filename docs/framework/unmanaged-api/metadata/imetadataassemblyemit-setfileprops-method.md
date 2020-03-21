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
ms.openlocfilehash: 25baa6ffda3d50915cc7898275d6a557c1b3e947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176034"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="edb04-102">IMetaDataAssemblyEmit::SetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="edb04-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="edb04-103">지정된 `File` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="edb04-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edb04-104">구문</span><span class="sxs-lookup"><span data-stu-id="edb04-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edb04-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="edb04-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="edb04-106">【인】 수정할 `File` 메타데이터 구조를 지정하는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="edb04-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="edb04-107">【인】 파일과 연결된 해시 데이터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="edb04-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="edb04-108">【인】 의 바이트 크기입니다. `pbHashValue`</span><span class="sxs-lookup"><span data-stu-id="edb04-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="edb04-109">【인】 파일의 다양한 특성을 지정하는 [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="edb04-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edb04-110">설명</span><span class="sxs-lookup"><span data-stu-id="edb04-110">Remarks</span></span>  
 <span data-ttu-id="edb04-111">`File` 메타데이터 구조를 만들려면 [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="edb04-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edb04-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="edb04-112">Requirements</span></span>  
 <span data-ttu-id="edb04-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="edb04-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edb04-114">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="edb04-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="edb04-115">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="edb04-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="edb04-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edb04-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb04-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="edb04-117">See also</span></span>

- [<span data-ttu-id="edb04-118">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="edb04-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
