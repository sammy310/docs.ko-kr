---
description: '자세히 알아보기: CreateCoreClrDebugTarget 함수'
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
ms.openlocfilehash: 30a6af29e6e1a6ee2c827049a3c792f2d663a702
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661578"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="614c0-103">CreateCoreClrDebugTarget 함수</span><span class="sxs-lookup"><span data-stu-id="614c0-103">CreateCoreClrDebugTarget Function</span></span>

<span data-ttu-id="614c0-104">원격 컴퓨터에서 실행 되는 디버거 프록시에 대 한 연결을 만들고, 원격 컴퓨터에서 실행 중인 프로세스 및 로드 된 런타임을 쿼리 하는 데 사용할 수 있는 [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="614c0-104">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="614c0-105">구문</span><span class="sxs-lookup"><span data-stu-id="614c0-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="614c0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="614c0-106">Parameters</span></span>  

 `dwAddress`  
 <span data-ttu-id="614c0-107">[in] 원격 대상 컴퓨터의 IPv4 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="614c0-107">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="614c0-108">제한이 생성 될 [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) 개체에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="614c0-108">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="614c0-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="614c0-109">Return Value</span></span>  

 <span data-ttu-id="614c0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="614c0-110">S_OK</span></span>  
 <span data-ttu-id="614c0-111">프로세스의 CLR 수가 성공적으로 확인되었으며 해당 핸들 및 경로 배열이 제대로 채워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="614c0-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="614c0-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="614c0-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="614c0-113">`ppTarget`에 대해 충분한 메모리를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="614c0-113">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="614c0-114">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="614c0-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="614c0-115">기타 실패</span><span class="sxs-lookup"><span data-stu-id="614c0-115">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="614c0-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="614c0-116">Requirements</span></span>  

 <span data-ttu-id="614c0-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="614c0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="614c0-118">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="614c0-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="614c0-119">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="614c0-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="614c0-120">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="614c0-120">**.NET Framework Versions:** 3.5 SP1</span></span>
