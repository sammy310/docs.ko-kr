---
title: IMetaDataImport2::GetPEKind 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9dda1fb38546138d52b5fe61754d5497e676c37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777418"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="28476-102">IMetaDataImport2::GetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="28476-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="28476-103">가져옵니다는 pe (이식 가능)에서 코드의 특성을 식별 하는 값 파일을 일반적으로 DLL 또는 EXE 파일을 현재 메타 데이터 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28476-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28476-104">구문</span><span class="sxs-lookup"><span data-stu-id="28476-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28476-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="28476-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="28476-106">[out] 값에 대 한 포인터를 [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) PE 파일을 설명 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="28476-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="28476-107">[out] 컴퓨터의 아키텍처를 식별 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="28476-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="28476-108">가능한 값은 다음 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="28476-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28476-109">설명</span><span class="sxs-lookup"><span data-stu-id="28476-109">Remarks</span></span>  
 <span data-ttu-id="28476-110">참조 하는 값을 `pdwMachine` 매개 변수는 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28476-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="28476-111">값</span><span class="sxs-lookup"><span data-stu-id="28476-111">Value</span></span>|<span data-ttu-id="28476-112">컴퓨터 아키텍처</span><span class="sxs-lookup"><span data-stu-id="28476-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="28476-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="28476-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="28476-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="28476-114">0x014C</span></span>|<span data-ttu-id="28476-115">x86</span><span class="sxs-lookup"><span data-stu-id="28476-115">x86</span></span>|  
|<span data-ttu-id="28476-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="28476-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="28476-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="28476-117">0x0200</span></span>|<span data-ttu-id="28476-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="28476-118">Intel IPF</span></span>|  
|<span data-ttu-id="28476-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="28476-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="28476-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="28476-120">0x8664</span></span>|<span data-ttu-id="28476-121">X64</span><span class="sxs-lookup"><span data-stu-id="28476-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28476-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28476-122">Requirements</span></span>  
 <span data-ttu-id="28476-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="28476-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28476-124">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="28476-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28476-125">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="28476-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28476-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28476-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28476-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="28476-127">See also</span></span>

- [<span data-ttu-id="28476-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28476-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="28476-129">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28476-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="28476-130">CorPEKind 열거형</span><span class="sxs-lookup"><span data-stu-id="28476-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
