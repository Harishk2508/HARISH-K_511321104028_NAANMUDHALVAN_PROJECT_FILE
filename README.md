# HARISH-K_511321104028_NAANMUDHALVAN_PROJECT_FILE

FOR GITHUB README FILE:


PROJECT CREATED BY:

NAME: HARISH K

REGISTER NO: 511321104028

COLLEGE CODE: 5113

COLLEGE NAME:KINGSTON ENGINEERING COLLEGE

LOGIN DETAILS:

USERNAME: admin

PASSWORD: admin


@PostMapping("/book")
    public String bookRoom(@RequestParam Long roomId, Model model) {
        Room room = roomService.findById(roomId);
        if (room != null && room.getAvailability() > 0) {
            room.setAvailability(room.getAvailability() - 1);
            roomService.save(room);
            
            // Generate a unique booking ID (you might want to use a more sophisticated method in a real application)
            String bookingId = "BK" + System.currentTimeMillis();
            
            // Add booking details to the model
            model.addAttribute("roomName", room.getName());
            model.addAttribute("roomType", room.getType());
            model.addAttribute("costPerPerson", room.getCostPerPerson());
            model.addAttribute("bookingId", bookingId);
            
            return "booking-success"; // This should match the name of your new HTML file (without the .html extension)
        } else {
            model.addAttribute("error", "Room booking failed. Please try again.");
            return "redirect:/rooms";
        }
    }
