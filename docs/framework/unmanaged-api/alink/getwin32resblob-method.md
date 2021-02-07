---
description: '자세히 알아보기: GetWin32ResBlob 메서드'
title: GetWin32ResBlob 메서드
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
ms.openlocfilehash: e1140b14bfba56dfac03c443a537d6d2188575b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718267"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="dc309-103">GetWin32ResBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="dc309-103">GetWin32ResBlob Method</span></span>

<span data-ttu-id="dc309-104">Win32 리소스 blob을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc309-104">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="dc309-105">어셈블리 옵션을 설정한 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc309-105">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc309-106">구문</span><span class="sxs-lookup"><span data-stu-id="dc309-106">Syntax</span></span>  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc309-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc309-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="dc309-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc309-108">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="dc309-109">Win32 버전 리소스를 생성할 때 사용할 파일 이름을 검색 하는 데 사용 되는 파일 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="dc309-109">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="dc309-110">파일이 DLL 이면 TRUE이 고, EXE의 경우 false입니다.</span><span class="sxs-lookup"><span data-stu-id="dc309-110">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="dc309-111">리소스 blob에 삽입할 선택적 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="dc309-111">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="dc309-112">리소스 blob을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="dc309-112">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="dc309-113">Blob의 크기를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc309-113">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc309-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="dc309-114">Return Value</span></span>  

 <span data-ttu-id="dc309-115">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc309-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc309-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc309-116">Requirements</span></span>  

 <span data-ttu-id="dc309-117">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="dc309-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc309-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc309-118">See also</span></span>

- [<span data-ttu-id="dc309-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc309-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="dc309-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc309-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="dc309-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="dc309-121">ALink API</span></span>](index.md)
