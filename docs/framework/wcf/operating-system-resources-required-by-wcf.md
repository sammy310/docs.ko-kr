---
title: WCF에 필요한 운영 체제 리소스
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: c2c26d769424a8d0655591cb10b4b13df8a15884
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961143"
---
# <a name="operating-system-resources-required-by-wcf"></a>WCF에 필요한 운영 체제 리소스

WCF (Windows Communication Foundation)는 작동 하기 위해 운영 체제에서 제공 하는 여러 리소스에 따라 달라 집니다. 다음 표에서는 이러한 리소스를 나열 합니다.

|리소스|설명|
|--------------|-----------------|
|MSDTC(Microsoft Distributed Transaction Coordinator)|OleTx 트랜잭션을 지원하는 데 필요합니다.|
|IIS(인터넷 정보 서비스)|IIS를 사용하여 애플리케이션을 호스트하려는 경우에 필요합니다.|
|WAS(Windows Process Activation Service)|WAS를 사용하여 애플리케이션을 호스트하려는 경우에 필요합니다.|
