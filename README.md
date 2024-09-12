import java.util.*;

public class RecomendadorDeFilmes {
    private static final Map<String, List<String>> filmesPorGenero = new HashMap<>();

    static {
        filmesPorGenero.put("Ação", Arrays.asList("Mad Max", "John Wick", "Die Hard"));
        filmesPorGenero.put("Comédia", Arrays.asList("Superbad", "The Hangover", "Groundhog Day"));
        filmesPorGenero.put("Drama", Arrays.asList("Forrest Gump", "The Shawshank Redemption", "Parasite"));
    }

    public static List<String> recomendar(String genero) {
        return filmesPorGenero.getOrDefault(genero, Collections.emptyList());
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Digite o gênero do filme que você gostaria de assistir:");
        String genero = scanner.nextLine();
        List<String> recomendacoes = recomendar(genero);
        if (recomendacoes.isEmpty()) {
            System.out.println("Gênero não encontrado. Tente novamente.");
        } else {
            System.out.println("Recomendações de filmes para o gênero " + genero + ":");
            for (String filme : recomendacoes) {
                System.out.println("- " + filme);
            }
        }
    }
}
