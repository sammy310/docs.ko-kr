---
description: '자세한 정보: 피어 투 피어 협업'
title: 피어 투 피어 협업
ms.date: 03/30/2017
ms.assetid: b6216d88-bccb-4a59-9f1c-9f751708e811
ms.openlocfilehash: 824ab3152c1ad765c2d19f5c6e719242255f606d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738282"
---
# <a name="peer-to-peer-collaboration"></a><span data-ttu-id="253e9-103">피어 투 피어 협업</span><span class="sxs-lookup"><span data-stu-id="253e9-103">Peer-to-peer collaboration</span></span>

<span data-ttu-id="253e9-104">피어 투 피어 네트워킹은 인터넷의 에지에서 클라이언트 기반 컴퓨팅 작업 이상을 수행하는 비교적 강력한 컴퓨터(개인용 컴퓨터)를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-104">Peer-to-peer networking is the utilization of the relatively powerful computers (personal computers) that exist at the edge of the Internet for more than just client-based computing tasks.</span></span> <span data-ttu-id="253e9-105">최신 개인용 컴퓨터(PC)에는 매우 빠른 프로세서, 광대한 메모리 및 대형 하드 디스크가 있으며, 이러한 리소스는 이메일과 웹 검색 등의 일반적인 컴퓨팅 작업을 수행할 때 완전히 이용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-105">The modern personal computer (PC) has a very fast processor, vast memory, and a large hard disk, none of which are being fully utilized when performing common computing tasks such as email and Web browsing.</span></span> <span data-ttu-id="253e9-106">최신 PC는 여러 형식의 애플리케이션을 위한 서버(피어) 및 클라이언트로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-106">The modern PC can easily act as both a client and server (a peer) for many types of applications.</span></span>  
  
<span data-ttu-id="253e9-107">피어 투 피어 협업 인프라는 Windows Vista 이상 플랫폼에서 주변 사람 찾기 서비스를 활용하는 Microsoft Windows 피어 투 피어 인프라의 간단한 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-107">The Peer-to-Peer Collaboration Infrastructure is a simplified implementation of the Microsoft Windows Peer-to-Peer Infrastructure that leverages the People Near Me service in Windows Vista and later platforms.</span></span> <span data-ttu-id="253e9-108">인터넷 엔드포인트와 연락처의 서비스도 제공할 수 있지만, 주변 사람 찾기 서비스가 작동하는 서브넷에서 피어 지원 애플리케이션용으로 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-108">It is best used for peer-enabled applications within a subnet for which the People Near Me service operates, although it can service internet endpoints or contacts as well.</span></span> <span data-ttu-id="253e9-109">연락처 엔드포인트, 가용성 및 현재 상태를 확인하기 위해 Live Messenger 및 기타 Live 인식 애플리케이션에서 사용하는 일반적인 연락처 관리자를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-109">It incorporates the common Contact Manager that is used by Live Messenger and other Live-aware applications to determine contact endpoints, availability, and presence.</span></span>  
  
## <a name="collaboration-applications"></a><span data-ttu-id="253e9-110">협업 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="253e9-110">Collaboration applications</span></span>

 <span data-ttu-id="253e9-111">일반적인 피어 투 피어 협업 애플리케이션은 다음 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-111">A typical peer-to-peer collaboration application is comprised of the following steps:</span></span>  
  
- <span data-ttu-id="253e9-112">피어는 협업 세션을 호스트하려는 피어의 ID를 판별합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-112">Peer determines the identity of a peer who is interested in hosting a collaboration session</span></span>  
  
- <span data-ttu-id="253e9-113">세션을 호스트하기 위한 요청을 보내면 호스트 피어가 협업 활동을 관리하도록 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-113">A request to host a session is sent, somehow, and the host peer agrees to manage collaboration activity.</span></span>  
  
- <span data-ttu-id="253e9-114">호스트에서 서브넷의 연락처(요청자 포함)를 세션에 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-114">The host invites contacts on the subnet (including the requestor) to a session.</span></span>  
  
- <span data-ttu-id="253e9-115">공동 작업하려는 모든 피어가 해당 연락처 관리자에 호스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-115">All peers who want to collaborate may add the host to their contact managers.</span></span>  
  
- <span data-ttu-id="253e9-116">대부분의 피어는 승인 또는 거부 여부에 상관없이 시기적절하게 호스트 피어에게 초대에 대한 응답을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-116">Most peers will send invitation responses, whether accepted or declined, back to the host peer in a timely fashion.</span></span>  
  
- <span data-ttu-id="253e9-117">공동 작업하려는 모든 피어는 호스트 피어에 가입합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-117">All peers who want to collaborate will subscribe to the host peer.</span></span>  
  
- <span data-ttu-id="253e9-118">피어가 초기 협업을 수행하는 동안 호스트 피어가 연락처 관리자에 원격 피어를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-118">While the peers are performing their initial collaboration activity, the host peer may add remote peers to its contact manager.</span></span> <span data-ttu-id="253e9-119">또한 승인, 거부 및 응답하지 않은 사람을 판별하기 위해 모든 초대 응답도 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-119">It also processes all invitation responses to determine who has accepted, who has declined, and who has not answered.</span></span>  <span data-ttu-id="253e9-120">응답하지 않은 사람에 대한 초대는 취소하거나 다른 활동을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-120">It may cancel invitations to those who have not answered, or perform some other activity.</span></span>  
  
- <span data-ttu-id="253e9-121">이때 호스트 피어는 초대된 모든 피어와 협업 세션을 시작하거나 애플리케이션을 협업 인프라에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-121">At this point, the host peer can start a collaboration session with all invited peers, or register an application with the collaboration infrastructure.</span></span>  <span data-ttu-id="253e9-122">P2P 애플리케이션에서는 피어 투 피어 협업 인프라와 <xref:System.Net.PeerToPeer.Collaboration> 네임스페이스를 사용하여 게임, 게시판, 회의 및 기타 서버가 없는 현재 상태 애플리케이션의 통신을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-122">P2P applications use the Peer-to-Peer Collaboration Infrastructure and the <xref:System.Net.PeerToPeer.Collaboration> namespace to coordinate communications for games, bulletin boards, conferencing, and other serverless presence applications.</span></span>  
  
## <a name="peer-to-peer-networking-security"></a><span data-ttu-id="253e9-123">피어 투 피어 네트워킹 보안</span><span class="sxs-lookup"><span data-stu-id="253e9-123">Peer-to-peer networking security</span></span>  

 <span data-ttu-id="253e9-124">Active Directory 도메인에서 도메인 컨트롤러는 Kerberos를 사용하여 인증 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-124">In an Active Directory domain, domain controllers provide authentication services using Kerberos.</span></span> <span data-ttu-id="253e9-125">서버 없는 피어 환경에서 피어는 자체 인증을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-125">In a serverless peer environment, the peers must provide their own authentication.</span></span> <span data-ttu-id="253e9-126">피어 투 피어 네트워킹의 경우 노드는 CA 역할을 수행할 수 있으므로, 각 피어의 신뢰할 수 있는 루트 저장소에서 루트 인증서의 요구 사항을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-126">For Peer-to-Peer Networking, any node can act as a CA, removing the requirement of a root certificate in each peer's trusted root store.</span></span> <span data-ttu-id="253e9-127">인증은 X.509 인증서 형식의 자체 서명된 인증서를 사용하여 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-127">Authentication is provided using self-signed certificates, formatted as X.509 certificates.</span></span> <span data-ttu-id="253e9-128">이러한 인증서는 퍼블릭 키/프라이빗 키 쌍을 생성하고 프라이빗 키를 사용하여 서명된 인증서를 생성하는 각 피어가 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-128">These are certificates that are created by each peer, which generates the public key/private key pair and the certificate that is signed using the private key.</span></span> <span data-ttu-id="253e9-129">자체 서명된 인증서는 피어 엔터티에 대한 정보를 제공하고 인증을 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-129">The self-signed certificate is used for authentication and to provide information about the peer entity.</span></span> <span data-ttu-id="253e9-130">X.509 인증과 마찬가지로 피어 네트워킹 인증은 신뢰할 수 있는 공개 키로 다시 추적되는 일련의 인증서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="253e9-130">Like X.509 authentication, peer networking authentication relies upon a chain of certificates tracing back to a public key that is trusted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="253e9-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="253e9-131">See also</span></span>

- <xref:System.Net.PeerToPeer.Collaboration>
- [<span data-ttu-id="253e9-132">System.Net.PeerToPeer.Collaboration 네임스페이스 정보</span><span class="sxs-lookup"><span data-stu-id="253e9-132">About the System.Net.PeerToPeer.Collaboration Namespace</span></span>](about-the-system-net-peertopeer-collaboration-namespace.md)
