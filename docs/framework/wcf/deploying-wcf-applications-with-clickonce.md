---
title: ClickOnce를 사용하여 WCF 애플리케이션 배포
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: 52657c5f3b5bc6c57c59f4ef23e73089f3c681eb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550373"
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="26ff5-102">ClickOnce를 사용하여 WCF 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="26ff5-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="26ff5-103">WCF (Windows Communication Foundation)를 사용 하는 클라이언트 응용 프로그램은 ClickOnce 기술을 사용 하 여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26ff5-103">Client applications using Windows Communication Foundation (WCF) may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="26ff5-104">클라이언트 응용 프로그램이 신뢰할 수 있는 인증서를 사용하여 디지털 방식으로 서명되는 경우, 이 기술을 통해 클라이언트 응용 프로그램은 코드 액세스 보안에서 제공하는 런타임 보안 보호의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26ff5-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="26ff5-105">ClickOnce 애플리케이션 서명에 사용되는 인증서는 신뢰할 수 있는 게시자 스토리지에 있어야 하며, 클라이언트 컴퓨터의 로컬 보안 정책은 게시자의 인증서를 사용하여 서명된 애플리케이션에 완전 신뢰 권한을 부여하도록 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ff5-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="26ff5-106">ClickOnce 응용 프로그램 및 신뢰할 수 있는 게시자 구성에 대 한 자세한 내용은 [clickonce의 신뢰할 수 있는 게시자 구성](/previous-versions/dotnet/articles/ms996418(v=msdn.10))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26ff5-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](/previous-versions/dotnet/articles/ms996418(v=msdn.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ff5-107">참조</span><span class="sxs-lookup"><span data-stu-id="26ff5-107">See also</span></span>

- [<span data-ttu-id="26ff5-108">신뢰할 수 있는 애플리케이션 배포 개요</span><span class="sxs-lookup"><span data-stu-id="26ff5-108">Trusted Application Deployment Overview</span></span>](/visualstudio/deployment/trusted-application-deployment-overview)
- <span data-ttu-id="26ff5-109">[Windows Forms 응용 프로그램에 대 한 ClickOnce 배포](/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="26ff5-109">[ClickOnce Deployment for Windows Forms Applications](/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))</span></span>
