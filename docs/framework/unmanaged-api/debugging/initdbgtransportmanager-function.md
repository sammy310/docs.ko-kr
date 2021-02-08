---
description: '자세히 알아보기: InitDbgTransportManager 함수'
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
ms.openlocfilehash: 19cdfcbe3a5b120c11fc781476410833997b8c6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790440"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="e5e92-103">InitDbgTransportManager 함수</span><span class="sxs-lookup"><span data-stu-id="e5e92-103">InitDbgTransportManager Function</span></span>

<span data-ttu-id="e5e92-104">프로세스 및 런타임 열거형의 원격 대상에 연결할 전송 관리자를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e92-104">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e92-105">구문</span><span class="sxs-lookup"><span data-stu-id="e5e92-105">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e5e92-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="e5e92-106">Return Value</span></span>  

 <span data-ttu-id="e5e92-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5e92-107">S_OK</span></span>  
 <span data-ttu-id="e5e92-108">성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e92-108">Success.</span></span>  
  
 <span data-ttu-id="e5e92-109">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e5e92-109">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="e5e92-110">함수가 전송 관리자에 대해 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e92-110">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="e5e92-111">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="e5e92-111">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="e5e92-112">기타 실패</span><span class="sxs-lookup"><span data-stu-id="e5e92-112">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5e92-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5e92-113">Requirements</span></span>  

 <span data-ttu-id="e5e92-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5e92-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5e92-115">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="e5e92-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="e5e92-116">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="e5e92-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="e5e92-117">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e5e92-117">**.NET Framework Versions:** 3.5 SP1</span></span>
