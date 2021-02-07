---
description: '자세히 알아보기: ICorDebugRemoteTarget 인터페이스'
title: ICorDebugRemoteTarget 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
ms.openlocfilehash: c6567ebb76c7a3c415c9978dc50941cb0b8985a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717877"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="7623e-103">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7623e-103">ICorDebugRemoteTarget Interface</span></span>

<span data-ttu-id="7623e-104">개발자가 CLR(공용 언어 런타임) 환경에서 Silverlight 기반 애플리케이션을 디버깅하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7623e-104">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7623e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7623e-105">Syntax</span></span>  
  
```cpp  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7623e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="7623e-106">Methods</span></span>  
  
|<span data-ttu-id="7623e-107">메서드</span><span class="sxs-lookup"><span data-stu-id="7623e-107">Method</span></span>|<span data-ttu-id="7623e-108">설명</span><span class="sxs-lookup"><span data-stu-id="7623e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7623e-109">ICorDebugRemoteTarget::GetHostName 메서드</span><span class="sxs-lookup"><span data-stu-id="7623e-109">ICorDebugRemoteTarget::GetHostName Method</span></span>](icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="7623e-110">원격 컴퓨터의 IP 주소나 호스트 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7623e-110">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7623e-111">설명</span><span class="sxs-lookup"><span data-stu-id="7623e-111">Remarks</span></span>  

 <span data-ttu-id="7623e-112">Windows 95, Windows 98, Windows ME 또는 x86이 아닌 플랫폼(IA-64, AMD64 등)에서는 관리 코드와 네이티브 코드가 혼합된 혼합 모드에서의 디버깅이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7623e-112">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7623e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7623e-113">Requirements</span></span>  

 <span data-ttu-id="7623e-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7623e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7623e-115">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="7623e-115">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="7623e-116">**Library:** : corguids .lib</span><span class="sxs-lookup"><span data-stu-id="7623e-116">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="7623e-117">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="7623e-117">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7623e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7623e-118">See also</span></span>

- [<span data-ttu-id="7623e-119">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7623e-119">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="7623e-120">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7623e-120">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="7623e-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7623e-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
