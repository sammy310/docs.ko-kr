---
title: ICLRMetadataLocator 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
ms.openlocfilehash: 642391bce99328f3700d1783054943b6a450b22b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789027"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="5babe-102">ICLRMetadataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5babe-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="5babe-103">데이터 액세스 서비스 계층에서 대상 프로세스의 어셈블리 메타 데이터를 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5babe-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5babe-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5babe-104">Methods</span></span>  
  
|<span data-ttu-id="5babe-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5babe-105">Method</span></span>|<span data-ttu-id="5babe-106">설명</span><span class="sxs-lookup"><span data-stu-id="5babe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5babe-107">GetMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="5babe-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="5babe-108">대상 프로세스에서 이미지의 메타 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5babe-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5babe-109">주의</span><span class="sxs-lookup"><span data-stu-id="5babe-109">Remarks</span></span>  
 <span data-ttu-id="5babe-110">API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5babe-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="5babe-111">예를 들어 라이브 프로세스에 대 한 구현은 메모리 덤프의 구현과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5babe-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5babe-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5babe-112">Requirements</span></span>  
 <span data-ttu-id="5babe-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5babe-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5babe-114">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="5babe-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5babe-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5babe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5babe-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5babe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5babe-117">참조</span><span class="sxs-lookup"><span data-stu-id="5babe-117">See also</span></span>

- [<span data-ttu-id="5babe-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5babe-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
