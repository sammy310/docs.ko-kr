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
ms.openlocfilehash: d335beecc12e0c1c895e42888ad7172f78062ff7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702540"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="7f0fa-102">IMetaDataImport2::GetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="7f0fa-102">IMetaDataImport2::GetPEKind Method</span></span>

<span data-ttu-id="7f0fa-103">현재 메타 데이터 범위에 정의 된 PE (이식 가능한 실행) 파일 (일반적으로 DLL 또는 EXE 파일)에 있는 코드의 특성을 식별 하는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7f0fa-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f0fa-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f0fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f0fa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f0fa-105">Parameters</span></span>  

 `pdwPEKind`  
 <span data-ttu-id="7f0fa-106">제한이 PE 파일을 설명 하는 [CorPEKind](corpekind-enumeration.md) 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7f0fa-106">[out] A pointer to a value of the [CorPEKind](corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="7f0fa-107">제한이 컴퓨터의 아키텍처를 식별 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7f0fa-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="7f0fa-108">가능한 값에 대해서는 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f0fa-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f0fa-109">설명</span><span class="sxs-lookup"><span data-stu-id="7f0fa-109">Remarks</span></span>  

 <span data-ttu-id="7f0fa-110">매개 변수에서 참조 하는 값은 `pdwMachine` 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f0fa-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="7f0fa-111">값</span><span class="sxs-lookup"><span data-stu-id="7f0fa-111">Value</span></span>|<span data-ttu-id="7f0fa-112">컴퓨터 아키텍처</span><span class="sxs-lookup"><span data-stu-id="7f0fa-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="7f0fa-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="7f0fa-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="7f0fa-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="7f0fa-114">0x014C</span></span>|<span data-ttu-id="7f0fa-115">x86</span><span class="sxs-lookup"><span data-stu-id="7f0fa-115">x86</span></span>|  
|<span data-ttu-id="7f0fa-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="7f0fa-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="7f0fa-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="7f0fa-117">0x0200</span></span>|<span data-ttu-id="7f0fa-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="7f0fa-118">Intel IPF</span></span>|  
|<span data-ttu-id="7f0fa-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="7f0fa-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="7f0fa-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="7f0fa-120">0x8664</span></span>|<span data-ttu-id="7f0fa-121">X64</span><span class="sxs-lookup"><span data-stu-id="7f0fa-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f0fa-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f0fa-122">Requirements</span></span>  

 <span data-ttu-id="7f0fa-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f0fa-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f0fa-124">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7f0fa-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f0fa-125">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f0fa-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f0fa-126">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f0fa-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f0fa-127">참조</span><span class="sxs-lookup"><span data-stu-id="7f0fa-127">See also</span></span>

- [<span data-ttu-id="7f0fa-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f0fa-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="7f0fa-129">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f0fa-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="7f0fa-130">CorPEKind 열거형</span><span class="sxs-lookup"><span data-stu-id="7f0fa-130">CorPEKind Enumeration</span></span>](corpekind-enumeration.md)
