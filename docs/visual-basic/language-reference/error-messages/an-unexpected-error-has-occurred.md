---
title: 단일 인스턴스 시작에 필요한 운영 체제 리소스를 가져올 수 없기 때문에 예기치 않은 오류가 발생했습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 9643d14b3e94e814c492b362b9db3e37cff4ce9f
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197381"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="ae2c8-102">단일 인스턴스 시작에 필요한 운영 체제 리소스를 가져올 수 없기 때문에 예기치 않은 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2c8-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="ae2c8-103">애플리케이션이 필요한 운영 체제 리소스를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2c8-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="ae2c8-104">이 문제가 발생할 수 있는 몇 가지 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2c8-104">Some of the possible causes for this problem are:</span></span>  
  
- <span data-ttu-id="ae2c8-105">애플리케이션에 명명된 운영 체제 개체를 만들 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2c8-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
- <span data-ttu-id="ae2c8-106">공용 언어 런타임에 메모리 매핑된 파일을 만들 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2c8-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
- <span data-ttu-id="ae2c8-107">애플리케이션이 운영 체제 개체에 액세스해야 하는데 다른 프로세스에서 해당 개체를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae2c8-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ae2c8-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ae2c8-108">To correct this error</span></span>  
  
1. <span data-ttu-id="ae2c8-109">애플리케이션에 명명된 운영 체제 개체를 만들 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2c8-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2. <span data-ttu-id="ae2c8-110">공용 언어 런타임에 메모리 매핑된 파일을 만들 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2c8-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3. <span data-ttu-id="ae2c8-111">컴퓨터를 다시 시작하여 원래 인스턴스 애플리케이션에 연결하는 데 필요한 리소스를 사용 중일 수 있는 프로세스를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ae2c8-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4. <span data-ttu-id="ae2c8-112">오류가 발생한 상황을 파악하여 Microsoft 기술 지원 서비스에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae2c8-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae2c8-113">참조</span><span class="sxs-lookup"><span data-stu-id="ae2c8-113">See also</span></span>

- [<span data-ttu-id="ae2c8-114">프로젝트 디자이너, 애플리케이션 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae2c8-114">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="ae2c8-115">디버거 기본 사항</span><span class="sxs-lookup"><span data-stu-id="ae2c8-115">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
- [<span data-ttu-id="ae2c8-116">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="ae2c8-116">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
