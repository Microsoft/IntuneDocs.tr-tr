<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD ve Intune kimlik bilgisi gereksinimleri

Kimlik doğrulaması ve yetkilendirme, Azure AD kimlik bilgileri ve Intune rol tabanlı erişim denetimine (RBAC) bağlıdır. Varsayılan olarak kiracınızdaki tüm genel yöneticiler ve Intune hizmet yöneticilerinin Veri ambarına erişimi vardır. Intune rolleri ile **Raporlama kaynağı** erişimi vererek daha fazla kullanıcının API’ye erişmesini sağlayabilirsiniz.

API dahil olmak üzere Intune Veri Ambarı’na erişim önkoşulları şöyledir:

  -  Kullanıcıya Intune lisansı atanmış olmalıdır
  -  Kullanıcı şunlardan biri olmalıdır:
      -  Azure AD genel yöneticisi
      -  Intune hizmet yöneticisi
      -  **Raporlar** kaynağına rol tabanlı erişimi olan kullanıcı