---
description: '자세히 알아보기: SetManifestFile 메서드'
title: SetManifestFile 메서드
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
ms.openlocfilehash: fe91c7f2b4e6f58a0a740de84e055ead49adb77d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662327"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="b653d-103">SetManifestFile 메서드</span><span class="sxs-lookup"><span data-stu-id="b653d-103">SetManifestFile Method</span></span>

<span data-ttu-id="b653d-104">링커가 어셈블리를 만들 때 사용 하는 매니페스트 파일을 지정 하거나 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b653d-104">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b653d-105">구문</span><span class="sxs-lookup"><span data-stu-id="b653d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b653d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b653d-106">Parameters</span></span>  

 `pszFile`  
  
 <span data-ttu-id="b653d-107">Win32 리소스 blob에 콘텐츠를 포함 하는 매니페스트 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b653d-107">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b653d-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="b653d-108">Return Value</span></span>  

 <span data-ttu-id="b653d-109">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b653d-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b653d-110">설명</span><span class="sxs-lookup"><span data-stu-id="b653d-110">Remarks</span></span>  

 <span data-ttu-id="b653d-111">Win32ResBlob를 요청 하기 전에이를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b653d-111">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="b653d-112">매개 변수 값은 `pszFile` 콘텐츠를 읽고 Win32 리소스에서 RT_MANIFEST ID가 있는 매니페스트 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b653d-112">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="b653d-113">NULL의 매개 변수를 사용 하 여 호출 하면 이전에 읽은 모든 매니페스트가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="b653d-113">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="b653d-114">이렇게 하면 링커가 초기화 시간의 상태를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b653d-114">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b653d-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b653d-115">Requirements</span></span>  

 <span data-ttu-id="b653d-116">ALink 필요</span><span class="sxs-lookup"><span data-stu-id="b653d-116">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b653d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b653d-117">See also</span></span>

- [<span data-ttu-id="b653d-118">IALink3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b653d-118">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="b653d-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="b653d-119">ALink API</span></span>](index.md)
- [<span data-ttu-id="b653d-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b653d-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b653d-121">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="b653d-121">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
