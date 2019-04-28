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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74cb2c7d1f79d23e1331cc7192ba2d6acfd9835c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761652"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="16d57-102">InitDbgTransportManager 함수</span><span class="sxs-lookup"><span data-stu-id="16d57-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="16d57-103">프로세스 및 런타임 열거형의 원격 대상에 연결할 전송 관리자를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="16d57-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d57-104">구문</span><span class="sxs-lookup"><span data-stu-id="16d57-104">Syntax</span></span>  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="16d57-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="16d57-105">Return Value</span></span>  
 <span data-ttu-id="16d57-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="16d57-106">S_OK</span></span>  
 <span data-ttu-id="16d57-107">명령 실행 성공</span><span class="sxs-lookup"><span data-stu-id="16d57-107">Success.</span></span>  
  
 <span data-ttu-id="16d57-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="16d57-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="16d57-109">함수가 전송 관리자에 대해 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16d57-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="16d57-110">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="16d57-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="16d57-111">기타 실패</span><span class="sxs-lookup"><span data-stu-id="16d57-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16d57-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16d57-112">Requirements</span></span>  
 <span data-ttu-id="16d57-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="16d57-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16d57-114">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="16d57-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="16d57-115">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="16d57-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="16d57-116">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="16d57-116">**.NET Framework Versions:** 3.5 SP1</span></span>
