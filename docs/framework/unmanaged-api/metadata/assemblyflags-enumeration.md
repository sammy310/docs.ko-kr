---
title: AssemblyFlags 열거형
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: 1cb84b94b37a2e9e8dd4d20d09cbca82db290c0f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009456"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="9b3aa-102">AssemblyFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="9b3aa-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="9b3aa-103">어셈블리의 런타임 기능을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b3aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b3aa-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9b3aa-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9b3aa-105">Members</span></span>  
  
|<span data-ttu-id="9b3aa-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9b3aa-106">Member</span></span>|<span data-ttu-id="9b3aa-107">설명</span><span class="sxs-lookup"><span data-stu-id="9b3aa-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="9b3aa-108">내보낸 형식 정의가 어셈블리를 구성 하는 파일 내에서 암시적 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="9b3aa-109">.NET Framework 버전 1.0 및 1.1에서는이 값이 항상 설정 된 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="9b3aa-110">어셈블리를 구성 하는 파일 내에서 리소스 정의가 암시적 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="9b3aa-111">.NET Framework 1.0 및 1.1에서는이 값이 항상 설정 된 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="9b3aa-112">동일한 응용 프로그램 도메인에서 실행 중인 경우 어셈블리를 다른 버전과 함께 실행할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="9b3aa-113">동일한 프로세스에서 실행 되는 어셈블리를 다른 버전과 함께 실행할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="9b3aa-114">동일한 컴퓨터에서 실행 중인 어셈블리를 다른 버전과 함께 실행할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b3aa-115">설명</span><span class="sxs-lookup"><span data-stu-id="9b3aa-115">Remarks</span></span>  
 <span data-ttu-id="9b3aa-116">0x0010 및 0x0070 (포함) 사이의 값은 참조 된 어셈블리의 병렬 호환성 기능을 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="9b3aa-117">이러한 값이 설정 되어 있지 않으면 어셈블리는 side-by-side 호환으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b3aa-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b3aa-118">Requirements</span></span>  
 <span data-ttu-id="9b3aa-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b3aa-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9b3aa-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="9b3aa-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b3aa-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b3aa-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b3aa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b3aa-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b3aa-123">See also</span></span>

- [<span data-ttu-id="9b3aa-124">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="9b3aa-124">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="9b3aa-125">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b3aa-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
