---
title: CreateCoreClrDebugTarget 함수
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: a7fed8cb70785f0ccfcadf1e16181db303ac98e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789191"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="f863e-102">CreateCoreClrDebugTarget 함수</span><span class="sxs-lookup"><span data-stu-id="f863e-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="f863e-103">원격 컴퓨터에서 실행 되는 디버거 프록시에 대 한 연결을 만들고, 원격 컴퓨터에서 실행 중인 프로세스 및 로드 된 런타임을 쿼리 하는 데 사용할 수 있는 [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f863e-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f863e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f863e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f863e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f863e-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="f863e-106">[in] 원격 대상 컴퓨터의 IPv4 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f863e-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="f863e-107">제한이 생성 될 [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) 개체에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f863e-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f863e-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="f863e-108">Return Value</span></span>  
 <span data-ttu-id="f863e-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="f863e-109">S_OK</span></span>  
 <span data-ttu-id="f863e-110">프로세스의 CLR 수가 성공적으로 확인되었으며 해당 핸들 및 경로 배열이 제대로 채워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="f863e-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="f863e-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f863e-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="f863e-112">`ppTarget`에 대해 충분한 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f863e-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="f863e-113">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="f863e-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="f863e-114">기타 실패</span><span class="sxs-lookup"><span data-stu-id="f863e-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f863e-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f863e-115">Requirements</span></span>  
 <span data-ttu-id="f863e-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f863e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f863e-117">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="f863e-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="f863e-118">**라이브러리:** mscordbi_macx86 .dll</span><span class="sxs-lookup"><span data-stu-id="f863e-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="f863e-119">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="f863e-119">**.NET Framework Versions:** 3.5 SP1</span></span>
