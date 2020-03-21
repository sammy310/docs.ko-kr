---
title: '방법: MMC 스냅인이 있는 인증서 보기'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184781"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="805bc-102">방법: MMC 스냅인이 있는 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="805bc-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="805bc-103">보안 클라이언트 또는 서비스를 만들 때 [인증서를](working-with-certificates.md) 자격 증명으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="805bc-104">예를 들어 일반적인 자격 증명 유형은 메서드를 사용하여 만드는 X.509 인증서입니다. <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="805bc-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="805bc-105">Windows 시스템에서 MMC(Microsoft 관리 콘솔)로 검사할 수 있는 세 가지 유형의 인증서 저장소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="805bc-106">로컬 컴퓨터: 저장소는 장치에 로컬이며 장치의 모든 사용자에게 전역입니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="805bc-107">현재 사용자: 저장소가 장치의 현재 사용자 계정에 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="805bc-108">서비스 계정: 저장소가 장치의 특정 서비스에 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="805bc-109">MMC 스냅인에서 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="805bc-109">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="805bc-110">다음 절차에서는 로컬 장치의 저장소를 검사하여 적절한 인증서를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="805bc-111">**시작** 메뉴에서 **실행을** 선택한 다음 *mmc*를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="805bc-112">MMC가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-112">The MMC appears.</span></span>
  
2. <span data-ttu-id="805bc-113">**파일** 메뉴에서 **스냅 추가/제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="805bc-113">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="805bc-114">**스냅인 추가 또는 제거 창이** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="805bc-115">사용 **가능한 스냅인** 목록에서 **인증서를**선택한 다음 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="805bc-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![인증서 스냅인 추가](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="805bc-117">인증서 **스냅인** 창에서 컴퓨터 **계정을**선택한 다음 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="805bc-118">선택적으로 특정 서비스에 대한 현재 사용자 또는 서비스 계정에 대한 **내 사용자** **계정을** 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="805bc-119">기기의 관리자가 아닌 경우 사용자 계정에 대해서만 인증서를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="805bc-120">컴퓨터 **선택** 창에서 **로컬 컴퓨터를** 선택한 다음 **완료를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="805bc-121">**스냅인 추가 또는 제거** 창에서 **확인을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![인증서 스냅인 추가](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="805bc-123">선택 사항: **파일** 메뉴에서 **저장** 또는 **저장을** 선택하여 나중에 사용할 수 있도록 MMC 콘솔 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="805bc-124">MMC 스냅인에서 인증서를 보려면 왼쪽 창에서 **콘솔 루트를** 선택한 다음 **인증서(로컬 컴퓨터)를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="805bc-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="805bc-125">각 인증서 유형에 대한 디렉터리 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="805bc-126">각 인증서 디렉터리에서 해당 인증서를 보고, 내보내고, 가져오고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="805bc-127">인증서 관리자 도구를 사용하여 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="805bc-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="805bc-128">인증서 관리자 도구를 사용하여 인증서를 보고, 내보내고, 가져오고, 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="805bc-129">로컬 장치에 대한 인증서를 보려면</span><span class="sxs-lookup"><span data-stu-id="805bc-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="805bc-130">**시작** 메뉴에서 **실행을** 선택한 다음 *certlm.msc를*입력합니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="805bc-131">로컬 장치에 대한 인증서 관리자 도구가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-131">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="805bc-132">인증서를 보려면 인증서 **-** 왼쪽 창에 있는 로컬 컴퓨터 아래에서 보려는 인증서 유형에 대한 디렉터리를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="805bc-133">현재 사용자의 인증서를 보려면</span><span class="sxs-lookup"><span data-stu-id="805bc-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="805bc-134">**시작** 메뉴에서 **실행을** 선택한 다음 *certmgr.msc를*입력합니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="805bc-135">현재 사용자의 인증서 관리자 도구가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-135">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="805bc-136">인증서를 보려면 인증서 **-** 왼쪽 창의 현재 사용자 아래에서 보려는 인증서 유형에 대한 디렉터리를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="805bc-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="805bc-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="805bc-137">See also</span></span>

- [<span data-ttu-id="805bc-138">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="805bc-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="805bc-139">방법: 개발 중에 사용할 임시 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="805bc-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="805bc-140">방법: 인증서의 지문 검색</span><span class="sxs-lookup"><span data-stu-id="805bc-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
