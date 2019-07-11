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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 502e7841f8c413aa48732bcea0b6c2178d70c061
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776440"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="54f24-102">AssemblyFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="54f24-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="54f24-103">어셈블리의 런타임 기능을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f24-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f24-104">구문</span><span class="sxs-lookup"><span data-stu-id="54f24-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="54f24-105">멤버</span><span class="sxs-lookup"><span data-stu-id="54f24-105">Members</span></span>  
  
|<span data-ttu-id="54f24-106">멤버</span><span class="sxs-lookup"><span data-stu-id="54f24-106">Member</span></span>|<span data-ttu-id="54f24-107">Description</span><span class="sxs-lookup"><span data-stu-id="54f24-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="54f24-108">내보낸된 형식 정의 어셈블리를 구성 하는 파일 내에서 암시적 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f24-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="54f24-109">.NET Framework 버전 1.0 및 1.1에서는이 값은 항상 설정으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f24-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="54f24-110">리소스 정의 어셈블리를 구성 하는 파일 내에서 암시적 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f24-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="54f24-111">.NET Framework 1.0 및 1.1에서는이 값은 항상 설정할으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f24-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="54f24-112">동일한 응용 프로그램 도메인에서 어셈블리를 다른 버전과 함께 실행할 수 없습니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f24-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="54f24-113">동일한 프로세스에서 어셈블리를 다른 버전과 함께 실행할 수 없습니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f24-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="54f24-114">동일한 컴퓨터에 어셈블리를 다른 버전과 함께 실행할 수 없습니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f24-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54f24-115">설명</span><span class="sxs-lookup"><span data-stu-id="54f24-115">Remarks</span></span>  
 <span data-ttu-id="54f24-116">0x0010 사이의 경계가 0x0070 값 참조 된 어셈블리의 side-by-side-호환성 기능을 설명 하기 위해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f24-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="54f24-117">이러한 값을 설정 하는 경우 어셈블리는 side-by-side-호환 되는 수로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f24-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54f24-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54f24-118">Requirements</span></span>  
 <span data-ttu-id="54f24-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="54f24-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54f24-120">**헤더:** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="54f24-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="54f24-121">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="54f24-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="54f24-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54f24-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f24-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="54f24-123">See also</span></span>

- [<span data-ttu-id="54f24-124">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="54f24-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="54f24-125">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54f24-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
