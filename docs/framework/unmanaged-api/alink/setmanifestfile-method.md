---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b293c30060107d18c6b609efc82c4128a73cc1c7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787200"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="c170c-102">SetManifestFile 메서드</span><span class="sxs-lookup"><span data-stu-id="c170c-102">SetManifestFile Method</span></span>
<span data-ttu-id="c170c-103">링커가 어셈블리를 만들 때 사용 하는 매니페스트 파일을 지정 하거나 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c170c-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c170c-104">구문</span><span class="sxs-lookup"><span data-stu-id="c170c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c170c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c170c-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="c170c-106">Win32 리소스 blob에 콘텐츠를 포함 하는 매니페스트 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c170c-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c170c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c170c-107">Return Value</span></span>  
 <span data-ttu-id="c170c-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c170c-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c170c-109">설명</span><span class="sxs-lookup"><span data-stu-id="c170c-109">Remarks</span></span>  
 <span data-ttu-id="c170c-110">Win32ResBlob를 요청 하기 전에이를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c170c-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="c170c-111">`pszFile` 매개 변수 값은 콘텐츠를 읽고 Win32 리소스에서 ID가 RT_MANIFEST 인 매니페스트 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c170c-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="c170c-112">NULL의 매개 변수를 사용 하 여 호출 하면 이전에 읽은 모든 매니페스트가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="c170c-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="c170c-113">이렇게 하면 링커가 초기화 시간의 상태를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c170c-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c170c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c170c-114">Requirements</span></span>  
 <span data-ttu-id="c170c-115">ALink 필요</span><span class="sxs-lookup"><span data-stu-id="c170c-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c170c-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="c170c-116">See also</span></span>

- [<span data-ttu-id="c170c-117">IALink3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c170c-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="c170c-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="c170c-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="c170c-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c170c-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c170c-120">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="c170c-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
