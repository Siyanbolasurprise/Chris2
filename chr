// app/page.tsx
import { Metadata } from 'next';

export const metadata: Metadata = {
  title: 'Formulaire de contact',
  description: 'Contactez-nous via ce formulaire',
};

export default function ContactPage() {
  const handleSubmit = async (e: React.FormEvent<HTMLFormElement>) => {
    e.preventDefault();
    
    const formData = new FormData(e.currentTarget);
    const data = Object.fromEntries(formData);

    // Exemple d'envoi (à adapter avec votre API ou service d'email)
    try {
      const res = await fetch('/api/contact', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(data),
      });

      if (res.ok) {
        alert('Merci ! Votre message a bien été envoyé.');
        e.currentTarget.reset();
      } else {
        alert('Une erreur est survenue. Veuillez réessayer.');
      }
    } catch (error) {
      alert('Erreur de connexion. Veuillez vérifier votre réseau.');
    }
  };

  return (
    <>
      <div className="min-h-screen bg-gray-50 py-12 px-4 sm:px-6 lg:px-8">
        <div className="max-w-3xl mx-auto">
          {/* En-tête */}
          <div className="text-center mb-10">
            <h1 className="text-4xl font-bold text-gray-900 mb-4">
              Contactez-nous
            </h1>
            <p className="text-lg text-gray-600">
              Nous serions ravis d’avoir de vos nouvelles. Remplissez le formulaire ci-dessous et nous vous répondrons dans les plus brefs délais.
            </p>
          </div>

          {/* Formulaire */}
          <div className="bg-white shadow-xl rounded-lg p-8">
            <form onSubmit={handleSubmit} className="space-y-6">
              <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
                {/* Nom */}
                <div>
                  <label htmlFor="nom" className="block text-sm font-medium text-gray-700 mb-1">
                    Nom complet <span className="text-red-500">*</span>
                  </label>
                  <input
                    type="text"
                    id="nom"
                    name="nom"
                    required
                    className="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-blue-500 focus:border-transparent outline-none transition"
                    placeholder="Jean Dupont"
                  />
                </div>

                {/* Email */}
                <div>
                  <label htmlFor="email" className="block text-sm font-medium text-gray-700 mb-1">
                    Adresse e-mail <span className="text-red-500">*</span>
                  </label>
                  <input
                    type="email"
                    id="email"
                    name="email"
                    required
                    className="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-blue-500 focus:border-transparent outline-none transition"
                    placeholder="jean.dupont@exemple.com"
                  />
                </div>
              </div>

              {/* Téléphone */}
              <div>
                <label htmlFor="telephone" className="block text-sm font-medium text-gray-700 mb-1">
                  Téléphone (facultatif)
                </label>
                <input
                  type="tel"
                  id="telephone"
                  name="telephone"
                  className="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-blue-500 focus:border-transparent outline-none transition"
                  placeholder="06 12 34 56 78"
                />
              </div>

              {/* Sujet */}
              <div>
                <label htmlFor="sujet" className="block text-sm font-medium text-gray-700 mb-1">
                  Sujet <span className="text-red-500">*</span>
                </label>
                <select
                  id="sujet"
                  name="sujet"
                  required
                  className="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-blue-500 focus:border-transparent outline-none transition"
                >
                  <option value="">Choisissez un sujet</option>
                  <option value="information">Demande d’information</option>
                  <option value="support">Support technique</option>
                  <option value="partenariat">Proposition de partenariat</option>
                  <option value="autre">Autre</option>
                </select>
              </div>

              {/* Message */}
              <div>
                <label htmlFor="message" className="block text-sm font-medium text-gray-700 mb-1">
                  Votre message <span className="text-red-500">*</span>
                </label>
                <textarea
                  id="message"
                  name="message"
                  rows={6}
                  required
                  className="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-blue-500 focus:border-transparent outline-none transition resize-none"
                  placeholder="Décrivez votre demande en détail..."
                ></textarea>
              </div>

              {/* Case à cocher RGPD */}
              <div className="flex items-start">
                <input
                  type="checkbox"
                  id="rgpd"
                  name="rgpd"
                  required
                  className="mt-1 mr-3 h-4 w-4 text-blue-600 border-gray-300 rounded focus:ring-blue-500"
                />
                <label htmlFor="rgpd" className="text-sm text-gray-600">
                  J’accepte que mes données soient traitées conformément à la{' '}
                  <a href="/politique-confidentialite" className="text-blue-600 hover:underline">
                    politique de confidentialité
                  </a>{' '}
                  du site. <span className="text-red-500">*</span>
                </label>
              </div>

              {/* Bouton Envoyer */}
              <div className="pt-4">
                <button
                  type="submit"
                  className="w-full md:w-auto px-8 py-3 bg-blue-600 text-white font-medium rounded-md hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 transition duration-200"
                >
                  Envoyer le message
                </button>
              </div>
            </form>
          </div>

          {/* Pied de page informatif */}
          <div className="mt-10 text-center text-sm text-gray-500">
            <p>Nous répondons généralement sous 24 à 48 heures ouvrées.</p>
          </div>
        </div>
      </div>
    </>
  );
}
