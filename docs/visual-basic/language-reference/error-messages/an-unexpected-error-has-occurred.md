---
description: '자세한 정보: 단일 인스턴스 시작에 필요한 운영 체제 리소스를 가져올 수 없기 때문에 예기치 않은 오류가 발생 했습니다.'
title: 단일 인스턴스 시작에 필요한 운영 체제 리소스를 가져올 수 없기 때문에 예기치 않은 오류가 발생했습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 76f7bd43c05ea3bd46b352a791debac984ca8fcd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103610"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="4aeb1-103">단일 인스턴스 시작에 필요한 운영 체제 리소스를 가져올 수 없기 때문에 예기치 않은 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="4aeb1-103">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>

<span data-ttu-id="4aeb1-104">애플리케이션이 필요한 운영 체제 리소스를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4aeb1-104">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="4aeb1-105">이 문제가 발생할 수 있는 몇 가지 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4aeb1-105">Some of the possible causes for this problem are:</span></span>  
  
- <span data-ttu-id="4aeb1-106">애플리케이션에 명명된 운영 체제 개체를 만들 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4aeb1-106">The application does not have permissions to create named operating-system objects.</span></span>  
  
- <span data-ttu-id="4aeb1-107">공용 언어 런타임에 메모리 매핑된 파일을 만들 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4aeb1-107">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
- <span data-ttu-id="4aeb1-108">애플리케이션이 운영 체제 개체에 액세스해야 하는데 다른 프로세스에서 해당 개체를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aeb1-108">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4aeb1-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4aeb1-109">To correct this error</span></span>  
  
1. <span data-ttu-id="4aeb1-110">애플리케이션에 명명된 운영 체제 개체를 만들 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4aeb1-110">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2. <span data-ttu-id="4aeb1-111">공용 언어 런타임에 메모리 매핑된 파일을 만들 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4aeb1-111">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3. <span data-ttu-id="4aeb1-112">컴퓨터를 다시 시작하여 원래 인스턴스 애플리케이션에 연결하는 데 필요한 리소스를 사용 중일 수 있는 프로세스를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="4aeb1-112">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4. <span data-ttu-id="4aeb1-113">오류가 발생한 상황을 파악하여 Microsoft 기술 지원 서비스에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="4aeb1-113">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aeb1-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4aeb1-114">See also</span></span>

- [<span data-ttu-id="4aeb1-115">프로젝트 디자이너, 애플리케이션 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4aeb1-115">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="4aeb1-116">디버거 기본 사항</span><span class="sxs-lookup"><span data-stu-id="4aeb1-116">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
- [<span data-ttu-id="4aeb1-117">Visual Studio 피드백 옵션</span><span class="sxs-lookup"><span data-stu-id="4aeb1-117">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)
