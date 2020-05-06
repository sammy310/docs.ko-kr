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
ms.openlocfilehash: 734f8eaa7c520bbf1ad1208ece42751e967a208a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859725"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="c7554-102">ICLRMetadataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7554-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="c7554-103">데이터 액세스 서비스 계층에서 대상 프로세스의 어셈블리 메타 데이터를 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7554-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7554-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c7554-104">Methods</span></span>  
  
|<span data-ttu-id="c7554-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c7554-105">Method</span></span>|<span data-ttu-id="c7554-106">Description</span><span class="sxs-lookup"><span data-stu-id="c7554-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7554-107">GetMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="c7554-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="c7554-108">대상 프로세스에서 이미지의 메타 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7554-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7554-109">설명</span><span class="sxs-lookup"><span data-stu-id="c7554-109">Remarks</span></span>  
 <span data-ttu-id="c7554-110">API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7554-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="c7554-111">예를 들어 라이브 프로세스에 대 한 구현은 메모리 덤프의 구현과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7554-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7554-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7554-112">Requirements</span></span>  
 <span data-ttu-id="c7554-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7554-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7554-114">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="c7554-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c7554-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7554-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7554-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7554-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7554-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7554-117">See also</span></span>

- [<span data-ttu-id="c7554-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7554-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
