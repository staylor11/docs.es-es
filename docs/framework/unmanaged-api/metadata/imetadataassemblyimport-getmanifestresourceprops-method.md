---
title: "IMetaDataAssemblyImport::GetManifestResourceProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetManifestResourceProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29458b0b7afa5a0c0be908915b4fc91c85d28c72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="131d0-102">IMetaDataAssemblyImport::GetManifestResourceProps (Método)</span><span class="sxs-lookup"><span data-stu-id="131d0-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="131d0-103">Obtiene el conjunto de propiedades del recurso del manifiesto con la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="131d0-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="131d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="131d0-104">Syntax</span></span>  
  
```  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="131d0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="131d0-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="131d0-106">[in] Un `mdManifestResource` símbolo (token) que representa el recurso para el que se va a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="131d0-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="131d0-107">[out] El nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="131d0-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="131d0-108">[in] El tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="131d0-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="131d0-109">[out] Un puntero al número de caracteres anchos realmente devueltos en `szName`.</span><span class="sxs-lookup"><span data-stu-id="131d0-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="131d0-110">[out] Un puntero a un `mdFile` símbolo (token) o un `mdAssemblyRef` símbolo (token) que representa el archivo o ensamblado, respectivamente, que contiene el recurso.</span><span class="sxs-lookup"><span data-stu-id="131d0-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="131d0-111">[out] Un puntero a un valor que especifica el desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="131d0-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="131d0-112">[out] Un puntero a marcas que describen los metadatos aplicados a un recurso.</span><span class="sxs-lookup"><span data-stu-id="131d0-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="131d0-113">El valor de flags es una combinación de uno o varios [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="131d0-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="131d0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="131d0-114">Requirements</span></span>  
 <span data-ttu-id="131d0-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="131d0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="131d0-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="131d0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="131d0-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="131d0-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="131d0-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="131d0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131d0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="131d0-119">See Also</span></span>  
 [<span data-ttu-id="131d0-120">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="131d0-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)