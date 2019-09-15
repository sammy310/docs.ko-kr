---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 4fc7a5021f9f8d9e6badcd3e13266fb8f4bfe7a4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991755"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="ad5b7-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="ad5b7-102">GetRawInputDevices</span></span>
<span data-ttu-id="ad5b7-103">PresentationHost.exe가 호스트 애플리케이션과 관련된 원시 입력 디바이스(휴먼 인터페이스 디바이스)를 검색할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5b7-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad5b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad5b7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad5b7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad5b7-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="ad5b7-106">제한이 원시 입력 장치를 열거 하는 [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) 에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5b7-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ad5b7-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="ad5b7-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="ad5b7-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="ad5b7-108">HRESULT:</span></span>  
  
 <span data-ttu-id="ad5b7-109">S_OK- [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) 는 s_ok가 반환 되는 경우에만 presentationhost.exe에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad5b7-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="ad5b7-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ad5b7-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad5b7-111">설명</span><span class="sxs-lookup"><span data-stu-id="ad5b7-111">Remarks</span></span>  
 <span data-ttu-id="ad5b7-112">원시 입력 디바이스는 키보드, 마우스 및 리모콘과 같은 덜 일반적인 디바이스를 포함하는 입력 디바이스 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="ad5b7-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="ad5b7-113">원시 입력 디바이스 목록이 검색된 후 PresentationHost.exe는 WM_INPUT 알림 메시지를 받을 디바이스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ad5b7-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5b7-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad5b7-114">See also</span></span>

- [<span data-ttu-id="ad5b7-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="ad5b7-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="ad5b7-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="ad5b7-116">FilterInputMessage</span></span>](filterinputmessage.md)
