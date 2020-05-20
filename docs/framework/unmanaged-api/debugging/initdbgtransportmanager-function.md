---
title: InitDbgTransportManager 함수
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
ms.openlocfilehash: e18ceb25b9c58a9710ef967cb071e3ef55beea8c
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421048"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="cf984-102">InitDbgTransportManager 함수</span><span class="sxs-lookup"><span data-stu-id="cf984-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="cf984-103">프로세스 및 런타임 열거형의 원격 대상에 연결할 전송 관리자를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="cf984-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf984-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf984-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="cf984-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="cf984-105">Return Value</span></span>  
 <span data-ttu-id="cf984-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf984-106">S_OK</span></span>  
 <span data-ttu-id="cf984-107">성공.</span><span class="sxs-lookup"><span data-stu-id="cf984-107">Success.</span></span>  
  
 <span data-ttu-id="cf984-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cf984-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="cf984-109">함수가 전송 관리자에 대해 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf984-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="cf984-110">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="cf984-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="cf984-111">기타 실패</span><span class="sxs-lookup"><span data-stu-id="cf984-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf984-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf984-112">Requirements</span></span>  
 <span data-ttu-id="cf984-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf984-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf984-114">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="cf984-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="cf984-115">**라이브러리:** mscordbi_macx86 .dll</span><span class="sxs-lookup"><span data-stu-id="cf984-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="cf984-116">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="cf984-116">**.NET Framework Versions:** 3.5 SP1</span></span>
